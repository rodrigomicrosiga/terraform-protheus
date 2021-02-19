# Provision ERP Protheus With Terraform and Ansible

Project for provisioning ERP Protheus development environment for code, build and test.
>This projetc use provider VMWare VSphere Hypervisor \
>This project use box Oracle Linux 8 for provisioning environment \
>This project user Jinja Templates for configure environment \
>Pay attention to **download the artifacts** to not have problems in provisioning

## Philosophy

This project aims to automate the provisioning of the ERP Protheus stack for development purposes.

## Getting Started

Fork the project and enjoy.\
Atention for pre requisites and License!!!

## Authors

Marcos Silvestrini\
marcos.silvestrini@gmail.com

## License

This project is licensed under the MIT License - see the LICENSE.md file for details

## Pre-Requisites

- [Git](https://git-scm.com/doc)
- [Terraform](https://www.terraform.io/downloads.html)
- [Python](https://www.python.org/doc/)

## References

- [Git](https://git-scm.com/doc)
- [VMWare VSphere](https://www.vmware.com/products/vsphere-hypervisor.html)
- [Terraform](https://www.terraform.io/)
- [Ansible](https://docs.ansible.com/ansible/2.5/modules/list_of_all_modules.html)
- [Postgresql](https://www.postgresql.org/download/linux/redhat/)
- [ODBC DSN](https://tdn.totvs.com/display/tec/DBAccess+-+Como+criar+uma+fonte+de+dados+para+uso+com+PostgreSQL)
- [Protheus Linux](https://tdn.totvs.com/pages/releaseview.action?pageId=515672176)
- [Blog Siga0984](https://siga0984.wordpress.com/2016/07/12/protheus-no-linux-parte-02)
- [Fix Error Invalid client library](https://tdn.totvs.com/display/tec/Melhoria+-+Suporte+ao+psqlODBC+09.01.0100)
- [Advplc Compiler](https://code.engpro.totvs.com.br/marcos.silvestrini/advplc-apply-patch)
- [Libs Protheus Linux](https://tdn.totvs.com/display/tec/Application+Server+-+Linux+packages)

## Stack Resources


SO: Oracle Linux 8\
CPU: 6 vcpus\
RAM: 8GB

SO: Windows 2019\
CPU: 3 vcpus\
RAM: 4GB

## Stack Version

Database: PostgreSQL 10.15\
Protheus: 12.1.27

## Install Terraform

### Download

```linux
foo
```

### Install

```linux
foo
```

## Create Box

1. clone this reposotory
2. Generate your ssh pub key and **copy to security/ folder**
3. Download artefacts of ERP(license,rpo,appserver,etc)
4. Copy artefacts for relative folders(license,rpo,appserver,etc)
5. foo
6. foo
7. foo
8. foo

## Provisioning Database Tasks

- Install and configure database
- Create database for app
- Create user and pass

## Provisioning App Tasks

- Instal and configure lockserver
- Instal and configure licenserver
- Install and configure dbaccess
- Install and configure appserver_boker
- Install and configure appserver_slaves
- Install and configure appserver_rest
- Install and configure appserver_soap

## Roles Short Explanations

### postgresql

Read the README file in the role folder for more details

### commom

This roles install commons libs,packages and create defaults paths.\
Libs and packages are described in defaults

### rpo

Role for configure rpo

### dictionay

Role for configure dictionary files, web files and portal files.

### license

Role for configure license server.

### dbaccess

Role for configure dbaccess,UnixODBC and postgresql-odbc

### appserver

Role for configure appservers.\
This role configure binaries for:\

- lockserver
- broker
- slaves
- soap
- rest


## Bugs

### Error in the  initialization enviroment in windows

Error:\
THREAD ERROR ([3728], marcos.silvestrini, SILVESTRINI)   11/02/2021   21:31:57\
TC_Open - NO CONNECTION on FWTABLEDDL:OPENTABLE(FWTABLEDDL.PRX) 13/10/2020 16:57:59\

Solution:\
Alter the odbc param UnknownSizes for longest or maximum in System DSN, restart all services and try it again
