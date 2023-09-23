<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 2000 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Cubet Techno Labs](https://cubettech.com)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[Many](https://www.many.co.uk)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel/)**
- **[OP.GG](https://op.gg)**
- **[WebReinvent](https://webreinvent.com/?utm_source=laravel&utm_medium=github&utm_campaign=patreon-sponsors)**
- **[Lendio](https://lendio.com)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
-- MySQL dump 10.13  Distrib 8.0.34, for Linux (x86_64)
--
-- Hos t: localhost    Database: gesprov
-- ------------------------------------------------------
-- Server version	8.0.34-0ubuntu0.22.04.1

/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!50503 SET NAMES utf8mb4 */;
/*!40103 SET @OLD_TIME_ZONE=@@TIME_ZONE */;
/*!40103 SET TIME_ZONE='+00:00' */;
/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;

--
-- Table structure for table `aceite_servicos`
--

DROP TABLE IF EXISTS `aceite_servicos`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `aceite_servicos` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_servico` int NOT NULL,
  `data` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `ip` varchar(20) NOT NULL,
  `assinatura` text,
  `id_resposta_solicitacao_assinatura_eletronica` int DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_aceite_servicos_id_servico` (`id_servico`),
  KEY `fk_aceite_servicos_resposta_idx` (`id_resposta_solicitacao_assinatura_eletronica`),
  CONSTRAINT `fk_aceite_servicos_id_servico` FOREIGN KEY (`id_servico`) REFERENCES `servicos` (`id`),
  CONSTRAINT `fk_aceite_servicos_resposta` FOREIGN KEY (`id_resposta_solicitacao_assinatura_eletronica`) REFERENCES `respostas_solicitacoes_assinaturas_eletronicas` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `aceite_servicos`
--

LOCK TABLES `aceite_servicos` WRITE;
/*!40000 ALTER TABLE `aceite_servicos` DISABLE KEYS */;
/*!40000 ALTER TABLE `aceite_servicos` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acessos`
--

DROP TABLE IF EXISTS `acessos`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acessos` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_servico` int NOT NULL,
  `id_setor` int NOT NULL,
  `velocidade_up` float NOT NULL,
  `velocidade_down` float NOT NULL,
  `id_servidor_ip_publico` int DEFAULT NULL,
  `id_tecnologia_ip_publico` int DEFAULT NULL,
  `informar_infraestrutura` tinyint(1) DEFAULT '1',
  `id_profile_radius` int DEFAULT NULL,
  `id_rede` int DEFAULT NULL,
  `id_pool` int DEFAULT NULL,
  `id_cto` int DEFAULT NULL,
  `ipv4` varchar(15) DEFAULT NULL,
  `framed_route` varchar(45) DEFAULT '',
  `ativar_ipv6` tinyint(1) DEFAULT '0',
  `id_ipv6_tunel_pppoe` varchar(255) DEFAULT NULL,
  `ipv6_tunel_pppoe` varchar(255) DEFAULT NULL,
  `ipv6_tunel_pppoe_posicao` int DEFAULT NULL,
  `id_ipv6_prefix_delegation` varchar(255) DEFAULT NULL,
  `ipv6_prefix_delegation` varchar(255) DEFAULT NULL,
  `ipv6_prefix_delegation_posicao` int DEFAULT NULL,
  `mac_onu` varchar(50) DEFAULT NULL,
  `ativar_burst` tinyint(1) NOT NULL,
  `mac` varchar(100) DEFAULT NULL,
  `serial_number` varchar(255) DEFAULT NULL,
  `observacao` varchar(255) DEFAULT NULL,
  `ativar_pppoe` tinyint NOT NULL,
  `usuario` varchar(50) DEFAULT NULL,
  `senha` varchar(50) DEFAULT NULL,
  `porta_web` int DEFAULT NULL,
  `porta_router` int NOT NULL,
  `dt_cadastro` datetime DEFAULT NULL,
  `posicao_cto` int DEFAULT NULL,
  `numero_serie_onu` varchar(50) DEFAULT NULL,
  `id_olt` int DEFAULT NULL,
  `id_placa` int DEFAULT NULL,
  `id_pon` int DEFAULT NULL,
  `vlan` int DEFAULT NULL,
  `tipo_onu` tinyint(1) DEFAULT NULL,
  `latitude` varchar(100) DEFAULT NULL,
  `longitude` varchar(100) DEFAULT NULL,
  `status` tinyint(1) DEFAULT '1',
  `id_tipo_servidor` int DEFAULT NULL,
  `id_pool_global` int DEFAULT NULL,
  `id_modelo_onu` int DEFAULT NULL,
  `etiqueta` varchar(255) DEFAULT NULL,
  `ipv4_global` varchar(45) DEFAULT NULL,
  `reducao` int DEFAULT '0',
  `id_tecnologia_dici` int DEFAULT NULL,
  `tipo_meio` int DEFAULT NULL,
  `sync_status` bigint DEFAULT '0',
  PRIMARY KEY (`id`),
  UNIQUE KEY `ipv4` (`ipv4`),
  UNIQUE KEY `usuario_UNIQUE` (`usuario`),
  KEY `fk_acessos_servico` (`id_servico`),
  KEY `fk_acessos_rede` (`id_rede`),
  KEY `fk_acessos_setor` (`id_setor`),
  KEY `fk_acessos_cto_idx` (`id_cto`),
  KEY `fk_acessos_servidor_ip_publico_idx` (`id_servidor_ip_publico`),
  KEY `fk_acessos_tecnologia_ip_publico_idx` (`id_tecnologia_ip_publico`),
  KEY `fk_acessos_pool_idx` (`id_pool`),
  KEY `fk_acessos_tipo_servidor_idx` (`id_tipo_servidor`),
  KEY `fk_acessos_pool_global_idx` (`id_pool_global`),
  KEY `fk_acessos_olt_idx` (`id_olt`),
  KEY `fk_acessos_placa_idx` (`id_placa`),
  KEY `fk_acessos_pon_idx` (`id_pon`),
  KEY `fk_acessos_modelo_onu_idx` (`id_modelo_onu`),
  KEY `fk_acessos_tecnologia_dici_idx` (`id_tecnologia_dici`),
  KEY `fk_acessos_profile_radius_idx` (`id_profile_radius`),
  CONSTRAINT `fk_acessos_cto` FOREIGN KEY (`id_cto`) REFERENCES `cto` (`id`) ON UPDATE CASCADE,
  CONSTRAINT `fk_acessos_modelo_onu` FOREIGN KEY (`id_modelo_onu`) REFERENCES `olts_modelos_onu_ont` (`id`),
  CONSTRAINT `fk_acessos_olt` FOREIGN KEY (`id_olt`) REFERENCES `olts` (`id`),
  CONSTRAINT `fk_acessos_placa` FOREIGN KEY (`id_placa`) REFERENCES `placas_pon` (`id`),
  CONSTRAINT `fk_acessos_pon` FOREIGN KEY (`id_pon`) REFERENCES `pons` (`id`),
  CONSTRAINT `fk_acessos_pool` FOREIGN KEY (`id_pool`) REFERENCES `pools_ips` (`id`),
  CONSTRAINT `fk_acessos_pool_global` FOREIGN KEY (`id_pool_global`) REFERENCES `pools_ips` (`id`),
  CONSTRAINT `fk_acessos_profile_radius` FOREIGN KEY (`id_profile_radius`) REFERENCES `profiles_radius` (`id`),
  CONSTRAINT `fk_acessos_rede` FOREIGN KEY (`id_rede`) REFERENCES `redes` (`id`),
  CONSTRAINT `fk_acessos_servico` FOREIGN KEY (`id_servico`) REFERENCES `servicos` (`id`),
  CONSTRAINT `fk_acessos_servidor_ip_publico` FOREIGN KEY (`id_servidor_ip_publico`) REFERENCES `servidores` (`id`),
  CONSTRAINT `fk_acessos_setor` FOREIGN KEY (`id_setor`) REFERENCES `setores` (`id`),
  CONSTRAINT `fk_acessos_tecnologia_dici` FOREIGN KEY (`id_tecnologia_dici`) REFERENCES `tecnologias_dici` (`id`),
  CONSTRAINT `fk_acessos_tecnologia_ip_publico` FOREIGN KEY (`id_tecnologia_ip_publico`) REFERENCES `tecnologias` (`id`),
  CONSTRAINT `fk_acessos_tipo_servidor` FOREIGN KEY (`id_tipo_servidor`) REFERENCES `tipos_servidor` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acessos`
--

LOCK TABLES `acessos` WRITE;
/*!40000 ALTER TABLE `acessos` DISABLE KEYS */;
/*!40000 ALTER TABLE `acessos` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acessos_anexos`
--

DROP TABLE IF EXISTS `acessos_anexos`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acessos_anexos` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_acesso` int DEFAULT NULL,
  `id_usuario` int DEFAULT NULL,
  `descricao` text,
  `extensao` varchar(10) DEFAULT NULL,
  `data` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  KEY `fk_acessos_anexo_acesso` (`id_acesso`),
  KEY `fk_acessos_anexo_usuario` (`id_usuario`),
  CONSTRAINT `fk_acessos_anexo_acesso` FOREIGN KEY (`id_acesso`) REFERENCES `acessos` (`id`),
  CONSTRAINT `fk_acessos_anexo_usuario` FOREIGN KEY (`id_usuario`) REFERENCES `usuarios` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acessos_anexos`
--

LOCK TABLES `acessos_anexos` WRITE;
/*!40000 ALTER TABLE `acessos_anexos` DISABLE KEYS */;
/*!40000 ALTER TABLE `acessos_anexos` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acessos_atualizar_radius`
--

DROP TABLE IF EXISTS `acessos_atualizar_radius`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acessos_atualizar_radius` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_acesso` int DEFAULT NULL,
  `data` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `status` tinyint(1) NOT NULL DEFAULT '0',
  `consulta` text,
  PRIMARY KEY (`id`),
  KEY `fk_acessos_redistribuir_ips_acessos` (`id_acesso`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acessos_atualizar_radius`
--

LOCK TABLES `acessos_atualizar_radius` WRITE;
/*!40000 ALTER TABLE `acessos_atualizar_radius` DISABLE KEYS */;
/*!40000 ALTER TABLE `acessos_atualizar_radius` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acessos_cto`
--

DROP TABLE IF EXISTS `acessos_cto`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acessos_cto` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_cto` int DEFAULT NULL,
  `id_acesso` int DEFAULT NULL,
  `data` datetime DEFAULT CURRENT_TIMESTAMP,
  `tipo` tinyint(1) DEFAULT '0',
  PRIMARY KEY (`id`),
  KEY `fk_acessos_cto_cto_idx` (`id_cto`),
  KEY `fk_acessos_cto_acessos_idx` (`id_acesso`),
  CONSTRAINT `fk_acessos_cto_acessos` FOREIGN KEY (`id_acesso`) REFERENCES `acessos` (`id`),
  CONSTRAINT `fk_acessos_cto_cto` FOREIGN KEY (`id_cto`) REFERENCES `cto` (`id`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acessos_cto`
--

LOCK TABLES `acessos_cto` WRITE;
/*!40000 ALTER TABLE `acessos_cto` DISABLE KEYS */;
/*!40000 ALTER TABLE `acessos_cto` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acessos_online`
--

DROP TABLE IF EXISTS `acessos_online`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acessos_online` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_acesso` int DEFAULT NULL,
  `id_servidor` int DEFAULT NULL,
  `servidor` varchar(255) DEFAULT NULL,
  `uptime` datetime DEFAULT NULL,
  `radius` tinyint(1) DEFAULT NULL,
  `ipv4` varchar(45) DEFAULT NULL,
  `status` tinyint(1) DEFAULT NULL,
  `data` datetime DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  KEY `fk_acessos_onlines_acesso_idx` (`id_acesso`),
  CONSTRAINT `fk_acessos_onlines_acesso` FOREIGN KEY (`id_acesso`) REFERENCES `acessos` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acessos_online`
--

LOCK TABLES `acessos_online` WRITE;
/*!40000 ALTER TABLE `acessos_online` DISABLE KEYS */;
/*!40000 ALTER TABLE `acessos_online` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acessos_redistribuir_ips`
--

DROP TABLE IF EXISTS `acessos_redistribuir_ips`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acessos_redistribuir_ips` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_acesso` int DEFAULT NULL,
  `data` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `status` tinyint(1) NOT NULL DEFAULT '0',
  PRIMARY KEY (`id`),
  KEY `fk_acessos_redistribuir_ips_acessos` (`id_acesso`),
  CONSTRAINT `fk_acessos_redistribuir_ips_acessos` FOREIGN KEY (`id_acesso`) REFERENCES `acessos` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acessos_redistribuir_ips`
--

LOCK TABLES `acessos_redistribuir_ips` WRITE;
/*!40000 ALTER TABLE `acessos_redistribuir_ips` DISABLE KEYS */;
/*!40000 ALTER TABLE `acessos_redistribuir_ips` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acoes_email`
--

DROP TABLE IF EXISTS `acoes_email`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acoes_email` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nome` varchar(45) DEFAULT NULL,
  `detalhe` varchar(45) DEFAULT NULL,
  `layout_email` longtext,
  `enviar` tinyint(1) DEFAULT NULL,
  `id_departamento` int DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_acoes_email_departamentos_idx` (`id_departamento`),
  CONSTRAINT `fk_acoes_email_departamentos` FOREIGN KEY (`id_departamento`) REFERENCES `departamentos` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=34 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acoes_email`
--

LOCK TABLES `acoes_email` WRITE;
/*!40000 ALTER TABLE `acoes_email` DISABLE KEYS */;
INSERT INTO `acoes_email` VALUES (1,'nota_gerada','Nota Fiscal Geração','<p>Prezado #NOME_CLIENTE#,</p><p>Segue anexo a nota fiscal do mês #COMPETENCIA#.</p>',0,2),(2,'servico_bloqueio','Serviço Bloqueio','<p>Prezado #NOME_CLIENTE#,</p><p>Seu serviço foi bloqueado!</p><p>Motivo: #MOTIVO#</p>',0,1),(3,'contas_receber_lembrete_vencimento','Lembrete Vencimento','<p>Prezado #NOME_CLIENTE#,</p><p>Este é um alerta automático para lembrá-lo que sua fatura vencerá no dia #DATA_CONTA#.</p><p>Boleto: #LINHA#.</p>',0,2),(5,'servico_ativacao','Serviço Ativação','<p>Prezado #NOME_CLIENTE#,</p><p>Seu serviço foi ativado!</p><p>Motivo: #MOTIVO#</p>',0,1),(6,'nota_cancelada','Nota Fiscal Cancelamento','<p>Prezado #NOME_CLIENTE#,</p><p>A nota fiscal do mês #COMPETENCIA# foi cancelada pelo sistema.</p>',0,2),(7,'segunda_via','Segunda via de boletos','<p>Prezado #NOME_CLIENTE#,</p><p>Segue anexo seus boletos</p>',0,2),(8,'nota_individual','Nota Fiscal Individual','<p>Prezado #NOME_CLIENTE#,</p><p>Segue anexo a nota fiscal do mês #COMPETENCIA#.</p>',0,2),(9,'servico_cancelamento','Serviço Cancelamento','<p>Prezado #NOME_CLIENTE#,</p><p>Seu serviço foi cancelado!</p><p>Motivo: #MOTIVO#</p>',0,1),(10,'servico_suspensao','Serviço Suspensão','<p>Prezado #NOME_CLIENTE#,</p><p>Seu serviço foi suspenso!</p><p>Motivo: #MOTIVO#</p>',0,1),(11,'chamado_abertura','Chamado Abertura','<p>Prezado #NOME_CLIENTE#,</p><p>Chamado aberto!</p><p>Relato do cliente: #RELATO_CLIENTE#</p>',0,1),(12,'chamado_fechamento','Chamado Fechamento','<p>Prezado #NOME_CLIENTE#,</p><p>Chamado fechamento!</p><p>Relato do cliente: #RELATO_CLIENTE#</p>',0,1),(13,'atendimento_abertura','Atendimento Abertura','<p>Prezado #NOME_CLIENTE#,</p><p>Atendimento aberto!</p><p>Relato do cliente: #RELATO_CLIENTE#</p>',0,1),(14,'atendimento_fechamento','Atendimento Fechamento','<p>Prezado #NOME_CLIENTE#,</p><p>Atendimento fechado!</p><p>Relato do cliente: #RELATO_CLIENTE#</p>',0,1),(15,'os_abertura','Os Abertura','<p>Prezado #NOME_CLIENTE#,</p><p>Ordem de serviço aberta!</p>',0,1),(16,'os_finalizar','Os Finalizar','<p>Prezado #NOME_CLIENTE#,</p><p>Ordem de serviço fechada!</p>',0,1),(17,'os_agendar','OS Agendamento','<p>Prezado #NOME_CLIENTE#,</p><p>Ordem de serviço agendada!</p>',0,1),(18,'backup_sucesso','Backup Automático Sucesso','<p>Backup gerado com sucesso para #PLATAFORMA#!</p>',0,1),(19,'backup_falha','Backup Automático Falha','<p>Erro ao gerar backup para #PLATAFORMA#!</p>',0,1),(20,'backup_manual','Backup Manual','<p>Backup manual gerado.!</p><p>Arquivo: #NOME_ARQUIVO#</p>',0,1),(21,'servico_desbloqueio_confianca','Serviço Desbloqueio em confiança','<p>Prezado #NOME_CLIENTE#,</p><p>Seu serviço foi desbloqueado em confiança!</p><p>Motivo: #MOTIVO#</p>',0,1),(22,'contrato_aceito','Aceite de contrato','<p>Prezado #NOME_CLIENTE#,</p><p>Segue anexo seu contrato</p>',0,1),(23,'servico_negativacao','Serviço Negativação','<p>Prezado #NOME_CLIENTE#,</p><p>Você está sendo negativado!</p><p>Motivo: #MOTIVO#</p>',0,1),(24,'servico_negociacao','Serviço Negociação','<p>Prezado #NOME_CLIENTE#,</p><p>Seu serviço está em negociação!</p><p>Motivo: #MOTIVO#</p>',0,1),(25,'contas_pagar_lembrete','Lembrete Contas a Pagar','<p>Contas pendentes com vencimentos para hoje: </p>#CONTAS_HOJE#<p>Contas pendentes com vencimentos para amanhã: </p>#CONTAS_AMANHA#',0,2),(26,'aniversario_cliente','Aniversário Cliente','<p>Olá #NOME_CLIENTE#,</p><p>Neste dia especial, a família #NOME_PROVEDOR# deseja a você felicidades e boas conexões. Parabéns pelo seu dia!</p>',0,1),(27,'contas_receber_lembrete_vencido','Lembrete Título Vencido','<p>Prezado #NOME_CLIENTE#,</p><p>Este é um alerta automático para lembrá-lo que sua fatura venceu no dia #DATA_CONTA#.</p><p>Boleto: #LINHA#.</p>',0,2),(28,'contas_receber_pagamento','Conta Receber Pagamento','<p>Prezado #NOME_CLIENTE#,</p><p>Recebemos o pagamento da sua fatura com vencimento #DATA_CONTA#, no valor de R$ #VALOR_CONTA#.</p><p>Boleto: #LINHA#.</p>',0,2),(29,'notas_lembrete','Lembrete Notas','<p>Faltam #QTD_DIAS# dias úteis para o final mês. Se atente as emissões de notas.</p>',0,2),(30,'retorno_suspensao_lembrete','Lembrete Retorno Suspensão','<p>Serviços que voltarão de suspensão:</p><p>#SERVICOS#</p>',0,2),(32,'lembrete_contrato_bloqueado','Lembrete Contrato Bloqueado','<p>Prezado #NOME_CLIENTE#,</p><p>Este é um alerta automático para lembrá-lo que seu serviço está bloqueado desde: #DATA_BLOQUEIO#</p>',0,2),(33,'segunda_via_contrato','Segunda via Contratos','<p>Prezado #NOME_CLIENTE#,</p><p>Segue anexo a segunda via do seu documento!</p>',1,1);
/*!40000 ALTER TABLE `acoes_email` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acoes_email_coringas`
--

DROP TABLE IF EXISTS `acoes_email_coringas`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acoes_email_coringas` (
  `id` int NOT NULL AUTO_INCREMENT,
  `coringa` varchar(45) DEFAULT NULL,
  `descricao` varchar(255) DEFAULT NULL,
  `id_acao_email` int DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_acoes_email_coringas_acoes_email_idx` (`id_acao_email`),
  CONSTRAINT `fk_acoes_email_coringas_acoes_email` FOREIGN KEY (`id_acao_email`) REFERENCES `acoes_email` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=65 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acoes_email_coringas`
--

LOCK TABLES `acoes_email_coringas` WRITE;
/*!40000 ALTER TABLE `acoes_email_coringas` DISABLE KEYS */;
INSERT INTO `acoes_email_coringas` VALUES (1,'#NOME_CLIENTE#','Nome do cliente',1),(2,'#COMPETENCIA#','Competência da geração de notas',1),(3,'#NOME_CLIENTE#','Nome do cliente',2),(4,'#MOTIVO#','Motivo escrito pelo usuario do sistema para o bloqueio',2),(5,'#NOME_CLIENTE#','Nome do cliente',5),(6,'#MOTIVO#','Motivo escrito pelo usuario do sistema para a ativação',5),(7,'#NOME_CLIENTE#','Nome do cliente',6),(8,'#COMPETENCIA#','Competência do cancelamento de notas',6),(9,'#NOME_CLIENTE#','Nome do cliente',7),(10,'#NOME_CLIENTE#','Nome do cliente',8),(11,'#COMPETENCIA#','Competência da notas',8),(12,'#NOME_CLIENTE#','Nome do cliente',9),(13,'#MOTIVO#','Motivo escrito pelo usuario do sistema para o cancelamento',9),(14,'#NOME_CLIENTE#','Nome do cliente',10),(15,'#MOTIVO#','Motivo escrito pelo usuario do sistema para a suspensão',10),(16,'#NOME_CLIENTE#','Nome do cliente',11),(17,'#RELATO_CLIENTE#','Relato do cliente escrito pelo usuario do sistema',11),(18,'#NOME_CLIENTE#','Nome do cliente',12),(19,'#RELATO_CLIENTE#','Relato do cliente escrito pelo usuario do sistema',12),(20,'#NOME_CLIENTE#','Nome do cliente',13),(21,'#RELATO_CLIENTE#','Relato do cliente escrito pelo usuario do sistema',13),(22,'#NOME_CLIENTE#','Nome do cliente',14),(23,'#RELATO_CLIENTE#','Relato do cliente escrito pelo usuario do sistema',14),(24,'#NOME_CLIENTE#','Nome do cliente',15),(25,'#NOME_CLIENTE#','Nome do cliente',16),(26,'#NOME_CLIENTE#','Nome do cliente',17),(27,'#PLATAFORMA#','Plataforma onde foi feito o backup',18),(28,'#PLATAFORMA#','Plataforma onde deu erro no backup',19),(29,'#NOME_ARQUIVO#','Nome de arquivo de backup gerado',20),(30,'#NOME_CLIENTE#','Nome do cliente',21),(31,'#MOTIVO#','Motivo escrito pelo usuario do sistema para o desbloqueio',21),(32,'#NOME_CLIENTE#','Nome do cliente',22),(33,'#NOME_CLIENTE#','Nome do cliente',23),(34,'#MOTIVO#','Motivo escrito pelo usuario do sistema para a negativação',23),(35,'#NOME_CLIENTE#','Nome do cliente',24),(36,'#MOTIVO#','Motivo escrito pelo usuario do sistema para a negociação',24),(37,'#CONTAS_HOJE#','Tabela com a listagem de contas a pagar do dia corrente',25),(38,'#CONTAS_AMANHA#','Tabela com a listagem de contas a pagar do dia seguinte ao corrente',25),(39,'#NOME_CLIENTE#','Nome do cliente no sistema',26),(40,'#NOME_PROVEDOR#','Nome do provedor',26),(41,'#NOME_CLIENTE#','Nome do cliente',3),(42,'#DATA_CONTA#','Data de vencimento da conta pendente',3),(43,'#VALOR_CONTA#','Valor da conta pendente',3),(44,'#LINHA#','Linha digitável do boleto',3),(45,'#LINHA#','Linha digitável do boleto',27),(46,'#VALOR_CONTA#','Valor da conta pendente',27),(47,'#DATA_CONTA#','Data de vencimento da conta pendente',27),(48,'#NOME_CLIENTE#','Nome do cliente',27),(52,'#NOME_CLIENTE#','Nome do cliente',28),(53,'#VALOR_CONTA#','Valor da conta paga',28),(54,'#DATA_CONTA#','Data de vencimento da conta paga',28),(55,'#LINHA#','Linha digitável do boleto',28),(56,'#QTD_DIAS#','Quantidade de dias úteis até o final do mês',29),(57,'#SERVICOS#','Lista de serviços que voltarão de suspensão',30),(58,'#NOME_PROVEDOR#','Nome do provedor',30),(59,'#NOME_CLIENTE#','Nome do cliente',32),(60,'#DATA_BLOQUEIO#','Data em que o serviço foi bloqueado',32),(61,'#SERVICO#','Nome do plano',32),(62,'#QTD_DIAS_UTEIS_BLOQUEIO#','Quantidade de dias uteis que o sistema será bloqueado após o vencimento',3),(63,'#QTD_DIAS_UTEIS_BLOQUEIO#','Quantidade de dias uteis que o sistema será bloqueado após o vencimento',27),(64,'#NOME_CLIENTE#','Nome do cliente',33);
/*!40000 ALTER TABLE `acoes_email_coringas` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acoes_gateway`
--

DROP TABLE IF EXISTS `acoes_gateway`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acoes_gateway` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nome` varchar(45) DEFAULT NULL,
  `detalhe` varchar(45) DEFAULT NULL,
  `layout_gateway` varchar(170) DEFAULT NULL,
  `enviar` tinyint(1) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acoes_gateway`
--

LOCK TABLES `acoes_gateway` WRITE;
/*!40000 ALTER TABLE `acoes_gateway` DISABLE KEYS */;
INSERT INTO `acoes_gateway` VALUES (1,'contas_receber_lembrete_vencimento','Lembrete Vencimento','Sua fatura: #LINHA#, no valor de R$ #VALOR_CONTA#, vencerá em #DATA_CONTA#. Caso pago, desconsidere.',0),(2,'contas_receber_lembrete_vencido','Lembrete Título Vencido','Nao identificamos o pagamento de sua fatura #DATA_CONTA# no valor de R$ #VALOR_CONTA#. Caso pago, desconsidere.',0),(3,'aniversario_cliente','Aniversário Cliente','Olá #NOME_CLIENTE#. Neste dia especial, a família #NOME_PROVEDOR# deseja a você felicidades  e boas conexões. Parabéns pelo seu dia!',0);
/*!40000 ALTER TABLE `acoes_gateway` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acoes_gateway_coringas`
--

DROP TABLE IF EXISTS `acoes_gateway_coringas`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acoes_gateway_coringas` (
  `id` int NOT NULL AUTO_INCREMENT,
  `coringa` varchar(45) DEFAULT NULL,
  `descricao` varchar(255) DEFAULT NULL,
  `id_acao_gateway` int DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_acoes_gateway_coringas_acoes_gateway_coringas_idx` (`id_acao_gateway`),
  CONSTRAINT `fk_acoes_gateway_coringas_acoes_gateway_coringas` FOREIGN KEY (`id_acao_gateway`) REFERENCES `acoes_gateway` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=13 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acoes_gateway_coringas`
--

LOCK TABLES `acoes_gateway_coringas` WRITE;
/*!40000 ALTER TABLE `acoes_gateway_coringas` DISABLE KEYS */;
INSERT INTO `acoes_gateway_coringas` VALUES (1,'#NOME_CLIENTE#','Nome do cliente',1),(2,'#DATA_CONTA#','Data de vencimento da conta pendente',1),(3,'#VALOR_CONTA#','Valor da conta pendente',1),(4,'#LINHA#','Linha digitável do boleto',1),(5,'#QTD_DIAS_UTEIS_BLOQUEIO#','Quantidade de dias uteis que o cliente será bloqueado após o vencimento',1),(6,'#NOME_CLIENTE#','Nome do cliente',2),(7,'#DATA_CONTA#','Data de vencimento da conta pendente',2),(8,'#VALOR_CONTA#','Valor da conta pendente',2),(9,'#LINHA#','Linha digitável do boleto',2),(10,'#QTD_DIAS_UTEIS_BLOQUEIO#','Quantidade de dias uteis que o cliente será bloqueado após o vencimento',2),(11,'#NOME_CLIENTE#','Nome do cliente no sistema',3),(12,'#NOME_PROVEDOR#','Nome do provedor',3);
/*!40000 ALTER TABLE `acoes_gateway_coringas` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acoes_push`
--

DROP TABLE IF EXISTS `acoes_push`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acoes_push` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nome` varchar(45) DEFAULT NULL,
  `detalhe` varchar(45) DEFAULT NULL,
  `layout_push` varchar(150) DEFAULT NULL,
  `enviar` tinyint(1) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acoes_push`
--

LOCK TABLES `acoes_push` WRITE;
/*!40000 ALTER TABLE `acoes_push` DISABLE KEYS */;
INSERT INTO `acoes_push` VALUES (1,'contas_receber_pagamento','Conta Receber Pagamento','Recebemos o pagamento da sua fatura com vencimento #DATA_CONTA#, no valor de R$ #VALOR_CONTA#.',0),(2,'contas_receber_lembrete_vencimento','Lembrete Vencimento','Sua fatura: #LINHA#, no valor de R$ #VALOR_CONTA#, vencerá em #DATA_CONTA#. Caso pago, desconsidere.',0),(3,'contas_receber_lembrete_vencido','Lembrete Título Vencido','Nao identificamos o pagamento de sua fatura #DATA_CONTA# no valor de R$ #VALOR_CONTA#. Caso pago, desconsidere.',0),(4,'aniversario_cliente','Aniversário Cliente','Olá #NOME_CLIENTE#. Neste dia especial, a família #NOME_PROVEDOR# deseja a você felicidades  e boas conexões. Parabéns pelo seu dia!',0);
/*!40000 ALTER TABLE `acoes_push` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acoes_push_coringas`
--

DROP TABLE IF EXISTS `acoes_push_coringas`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acoes_push_coringas` (
  `id` int NOT NULL AUTO_INCREMENT,
  `coringa` varchar(45) DEFAULT NULL,
  `descricao` varchar(255) DEFAULT NULL,
  `id_acao_push` int DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_acoes_push_coringas_acoes_push_coringas_idx` (`id_acao_push`),
  CONSTRAINT `fk_acoes_push_coringas_acoes_push_coringas` FOREIGN KEY (`id_acao_push`) REFERENCES `acoes_push` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=17 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acoes_push_coringas`
--

LOCK TABLES `acoes_push_coringas` WRITE;
/*!40000 ALTER TABLE `acoes_push_coringas` DISABLE KEYS */;
INSERT INTO `acoes_push_coringas` VALUES (1,'#NOME_CLIENTE#','Nome do cliente',1),(2,'#DATA_CONTA#','Data de vencimento da conta paga',1),(3,'#VALOR_CONTA#','Valor da conta paga',1),(4,'#LINHA#','Linha digitável do boleto',1),(5,'#NOME_CLIENTE#','Nome do cliente',2),(6,'#DATA_CONTA#','Data de vencimento da conta pendente',2),(7,'#VALOR_CONTA#','Valor da conta pendente',2),(8,'#LINHA#','Linha digitável do boleto',2),(9,'#NOME_CLIENTE#','Nome do cliente',3),(10,'#DATA_CONTA#','Data de vencimento da conta pendente',3),(11,'#VALOR_CONTA#','Valor da conta pendente',3),(12,'#LINHA#','Linha digitável do boleto',3),(13,'#NOME_CLIENTE#','Nome do cliente no sistema',4),(14,'#NOME_PROVEDOR#','Nome do provedor',4),(15,'#QTD_DIAS_UTEIS_BLOQUEIO#','Quantidade de dias uteis que o sistema será bloqueado após o vencimento',2),(16,'#QTD_DIAS_UTEIS_BLOQUEIO#','Quantidade de dias uteis que o sistema será bloqueado após o vencimento',3);
/*!40000 ALTER TABLE `acoes_push_coringas` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acoes_sms`
--

DROP TABLE IF EXISTS `acoes_sms`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acoes_sms` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nome` varchar(45) DEFAULT NULL,
  `detalhe` varchar(45) DEFAULT NULL,
  `layout_sms` varchar(145) DEFAULT NULL,
  `enviar` tinyint(1) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=9 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acoes_sms`
--

LOCK TABLES `acoes_sms` WRITE;
/*!40000 ALTER TABLE `acoes_sms` DISABLE KEYS */;
INSERT INTO `acoes_sms` VALUES (1,'aniversario_cliente','Aniversário Cliente','Olá #NOME_CLIENTE#. Neste dia especial, a família #NOME_PROVEDOR# deseja a você felicidades  e boas conexões. Parabéns pelo seu dia!',0),(2,'contas_pagar_lembrete','Lembrete Contas a Pagar','Contas pendentes com vencimentos para hoje: R$ #TOTAL_CONTAS_HOJE#. Contas pendentes com vencimentos para amanhã: R$ #TOTAL_CONTAS_AMANHA#.',0),(3,'contas_receber_lembrete_vencimento','Lembrete Vencimento','#NOME_PROVEDOR#: Passando para lembrá-lo que sua fatura com código de barras: #LINHA#, vencerá em #DATA_CONTA#.',0),(4,'contas_receber_lembrete_vencido','Lembrete Título Vencido','#NOME_PROVEDOR#: Passando para lembrá-lo que sua fatura com código de barras: #LINHA#, vencerá em #DATA_CONTA#.',0),(5,'contas_receber_pagamento','Conta Receber Pagamento','#NOME_PROVEDOR#: Recebemos o pagamento da sua fatura com vencimento #DATA_CONTA#, no valor de R$ #VALOR_CONTA#.',0),(6,'notas_lembrete','Lembrete Notas','Faltam #QTD_DIAS# dias úteis para o final mês. Se atente as emissões de notas.',0),(7,'retorno_suspensao_lembrete','Lembrete Retorno Suspensão','#NOME_PROVEDOR#: Número dos contratos de serviços que voltarão de suspensão: #CONTRATOS#',0),(8,'lembrete_contrato_bloqueado','Lembrete Contrato Bloqueado','Prezado #NOME_CLIENTE#, este é um alerta automático para lembrá-lo que seu serviço está bloqueado desde: #DATA_BLOQUEIO#',0);
/*!40000 ALTER TABLE `acoes_sms` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acoes_sms_coringas`
--

DROP TABLE IF EXISTS `acoes_sms_coringas`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acoes_sms_coringas` (
  `id` int NOT NULL AUTO_INCREMENT,
  `coringa` varchar(45) DEFAULT NULL,
  `descricao` varchar(255) DEFAULT NULL,
  `id_acao_sms` int DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_acoes_sms_coringas_acoes_sms_idx` (`id_acao_sms`),
  CONSTRAINT `fk_acoes_sms_coringas_acoes_sms` FOREIGN KEY (`id_acao_sms`) REFERENCES `acoes_sms` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=28 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acoes_sms_coringas`
--

LOCK TABLES `acoes_sms_coringas` WRITE;
/*!40000 ALTER TABLE `acoes_sms_coringas` DISABLE KEYS */;
INSERT INTO `acoes_sms_coringas` VALUES (1,'#NOME_CLIENTE#','Nome do cliente no sistema',1),(2,'#NOME_PROVEDOR#','Nome do provedor',1),(3,'#TOTAL_CONTAS_HOJE#','Valor total de contas a pagar do dia corrente',2),(4,'#TOTAL_CONTAS_AMANHA#','Valor total de contas a pagar do dia seguinte ao corrente',2),(5,'#NOME_CLIENTE#','Nome do cliente',3),(6,'#DATA_CONTA#','Data de vencimento da conta pendente',3),(7,'#VALOR_CONTA#','Valor da conta pendente',3),(8,'#LINHA#','Linha digitável do boleto',3),(9,'#NOME_PROVEDOR#','Nome do provedor',3),(10,'#NOME_CLIENTE#','Nome do cliente',4),(11,'#DATA_CONTA#','Data de vencimento da conta pendente',4),(12,'#VALOR_CONTA#','Valor da conta pendente',4),(13,'#LINHA#','Linha digitável do boleto',4),(14,'#NOME_PROVEDOR#','Nome do provedor',4),(15,'#DATA_CONTA#','Data de vencimento da conta paga',5),(16,'#VALOR_CONTA#','Valor da conta paga',5),(17,'#LINHA#','Linha digitável do boleto',5),(18,'#NOME_PROVEDOR#','Nome do provedor',5),(19,'#NOME_PROVEDOR#','Nome do provedor',4),(20,'#QTD_DIAS#','Quantidade de dias úteis até o final do mês',6),(21,'#CONTRATOS#','Número dos contratos que voltarão de suspensão',7),(22,'#NOME_PROVEDOR#','Nome do provedor',7),(23,'#NOME_CLIENTE#','Nome do cliente',8),(24,'#DATA_BLOQUEIO#','Data em que o serviço foi bloqueado',8),(25,'#SERVICO#','Nome do plano',8),(26,'#QTD_DIAS_UTEIS_BLOQUEIO#','Quantidade de dias uteis que o sistema será bloqueado após o vencimento',3),(27,'#QTD_DIAS_UTEIS_BLOQUEIO#','Quantidade de dias uteis que o sistema será bloqueado após o vencimento',4);
/*!40000 ALTER TABLE `acoes_sms_coringas` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acordos`
--

DROP TABLE IF EXISTS `acordos`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acordos` (
  `id` int NOT NULL AUTO_INCREMENT,
  `data_filtrar_parcelas` datetime DEFAULT CURRENT_TIMESTAMP,
  `contas_renegociar` varchar(255) DEFAULT NULL,
  `id_forma_pagamento` int DEFAULT NULL,
  `possui_entrada` int DEFAULT NULL,
  `possui_parcelas` int DEFAULT NULL,
  `id_servico` int DEFAULT NULL,
  `valor_total_renegociar` double DEFAULT NULL,
  `valor_acrescimo` double DEFAULT NULL,
  `valor_desconto` double DEFAULT NULL,
  `valor_total_a_pagar` double DEFAULT NULL,
  `valor_entrada` double DEFAULT NULL,
  `entrada_inclusa_mensalidade` tinyint(1) DEFAULT NULL,
  `vencimento_entrada` datetime DEFAULT NULL,
  `quantidade_parcelas` int DEFAULT NULL,
  `incluir_parcela_mensalidade` tinyint(1) DEFAULT NULL,
  `dia_vencimento_parcela` int DEFAULT NULL,
  `mes_inicio_parcelamento` int DEFAULT NULL,
  `id_usuario` int DEFAULT NULL,
  `data` datetime DEFAULT CURRENT_TIMESTAMP,
  `status` int DEFAULT '1' COMMENT '0 -> Cancelado\n1 -> Proposta\n2 -> Ativo\n3 -> Finalizado',
  `data_cancelamento` datetime DEFAULT NULL,
  `id_usuario_cancelamento` int DEFAULT NULL,
  `id_motivo_cancelamento` int DEFAULT NULL,
  `descricao_motivo_cancelamento` text,
  PRIMARY KEY (`id`),
  KEY `fk_acordos_usuarios_idx` (`id_usuario`),
  KEY `fk_acordos_servicos_idx` (`id_servico`),
  CONSTRAINT `fk_acordos_servicos` FOREIGN KEY (`id_servico`) REFERENCES `servicos` (`id`),
  CONSTRAINT `fk_acordos_usuarios` FOREIGN KEY (`id_usuario`) REFERENCES `usuarios` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acordos`
--

LOCK TABLES `acordos` WRITE;
/*!40000 ALTER TABLE `acordos` DISABLE KEYS */;
/*!40000 ALTER TABLE `acordos` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acordos_contas_receber`
--

DROP TABLE IF EXISTS `acordos_contas_receber`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acordos_contas_receber` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_acordo` int DEFAULT NULL,
  `id_conta_receber` int DEFAULT NULL,
  `tipo` tinyint(1) DEFAULT NULL,
  `entrada` tinyint(1) DEFAULT NULL,
  `parcela` tinyint(1) DEFAULT NULL,
  `numero_parcela` int DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_acordos_contas_receber_acordo_idx` (`id_acordo`),
  KEY `fk_acordos_contas_receber_conta_receber_idx` (`id_conta_receber`),
  CONSTRAINT `fk_acordos_contas_receber_acordo` FOREIGN KEY (`id_acordo`) REFERENCES `acordos` (`id`),
  CONSTRAINT `fk_acordos_contas_receber_conta_receber` FOREIGN KEY (`id_conta_receber`) REFERENCES `contas_receber` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acordos_contas_receber`
--

LOCK TABLES `acordos_contas_receber` WRITE;
/*!40000 ALTER TABLE `acordos_contas_receber` DISABLE KEYS */;
/*!40000 ALTER TABLE `acordos_contas_receber` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `acrescimo_mensalidade`
--

DROP TABLE IF EXISTS `acrescimo_mensalidade`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `acrescimo_mensalidade` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_servico` int DEFAULT NULL,
  `id_promocao` int DEFAULT NULL,
  `valor` float DEFAULT NULL,
  `mes_referencia` datetime DEFAULT NULL,
  `descricao` varchar(255) DEFAULT NULL,
  `primeiro_vencimento` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_acrescimo_servico_idx` (`id_servico`),
  KEY `fk_acrescimo_promocao_idx` (`id_promocao`),
  CONSTRAINT `fk_acrescimo_promocao` FOREIGN KEY (`id_promocao`) REFERENCES `promocoes` (`id`),
  CONSTRAINT `fk_acrescimo_servico` FOREIGN KEY (`id_servico`) REFERENCES `servicos` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `acrescimo_mensalidade`
--

LOCK TABLES `acrescimo_mensalidade` WRITE;
/*!40000 ALTER TABLE `acrescimo_mensalidade` DISABLE KEYS */;
/*!40000 ALTER TABLE `acrescimo_mensalidade` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `agendamento_adicionar_easytv`
--

DROP TABLE IF EXISTS `agendamento_adicionar_easytv`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `agendamento_adicionar_easytv` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_servico` int DEFAULT NULL,
  `id_integrador` int DEFAULT NULL,
  `operacao` varchar(50) DEFAULT NULL,
  `pacote` varchar(50) DEFAULT NULL,
  `data` datetime DEFAULT CURRENT_TIMESTAMP,
  `status` int DEFAULT '0',
  PRIMARY KEY (`id`),
  KEY `fk_agendamento_adicionar_easytv_id_servico_idx` (`id_servico`),
  KEY `fk_agendamento_adicionar_easytv_id_inegrador_idx` (`id_integrador`),
  CONSTRAINT `fk_agendamento_adicionar_easytv_id_inegrador` FOREIGN KEY (`id_integrador`) REFERENCES `integradores_sva` (`id`),
  CONSTRAINT `fk_agendamento_adicionar_easytv_id_servico` FOREIGN KEY (`id_servico`) REFERENCES `servicos` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `agendamento_adicionar_easytv`
--

LOCK TABLES `agendamento_adicionar_easytv` WRITE;
/*!40000 ALTER TABLE `agendamento_adicionar_easytv` DISABLE KEYS */;
/*!40000 ALTER TABLE `agendamento_adicionar_easytv` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `agendamento_envio_email`
--

DROP TABLE IF EXISTS `agendamento_envio_email`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `agendamento_envio_email` (
  `id` int NOT NULL AUTO_INCREMENT,
  `email_destinatario` varchar(255) DEFAULT NULL,
  `nome_destinatario` varchar(255) DEFAULT NULL,
  `assunto` varchar(255) DEFAULT NULL,
  `layout` text,
  `email_remetente` varchar(255) DEFAULT NULL,
  `senha_remetente` varchar(255) DEFAULT NULL,
  `nome_remetente` varchar(255) DEFAULT NULL,
  `caminho_anexo` varchar(255) DEFAULT NULL,
  `nome_anexo` varchar(255) DEFAULT NULL,
  `status` tinyint(1) NOT NULL DEFAULT '0',
  `data` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `agendamento_envio_email`
--

LOCK TABLES `agendamento_envio_email` WRITE;
/*!40000 ALTER TABLE `agendamento_envio_email` DISABLE KEYS */;
/*!40000 ALTER TABLE `agendamento_envio_email` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `agendamento_envio_notificacoes`
--

DROP TABLE IF EXISTS `agendamento_envio_notificacoes`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `agendamento_envio_notificacoes` (
  `id` int NOT NULL AUTO_INCREMENT,
  `email_destinatario` varchar(255) DEFAULT NULL,
  `nome_destinatario` varchar(255) DEFAULT NULL,
  `assunto` varchar(255) DEFAULT NULL,
  `layout` text,
  `conteudo` longtext,
  `email_remetente` varchar(255) DEFAULT NULL,
  `senha_remetente` varchar(255) DEFAULT NULL,
  `nome_remetente` varchar(255) DEFAULT NULL,
  `caminho_anexo` longtext,
  `nome_anexo` varchar(255) DEFAULT NULL,
  `telefones` varchar(255) DEFAULT NULL,
  `telefone_gateway` varchar(255) DEFAULT NULL,
  `tokens` longtext,
  `status_email` tinyint(1) NOT NULL DEFAULT '2',
  `status_telefone` tinyint(1) NOT NULL DEFAULT '2',
  `status_push` tinyint(1) NOT NULL DEFAULT '2',
  `status_gateway` tinyint(1) NOT NULL DEFAULT '2',
  `retorno` longtext,
  `id_usuario` int DEFAULT '1',
  `id_geracao_massa` int DEFAULT NULL,
  `id_servico` int DEFAULT NULL,
  `id_gateway_notificacao` int DEFAULT NULL,
  `status_central` tinyint(1) NOT NULL DEFAULT '0',
  `data` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `data_processamento_cron` datetime DEFAULT NULL,
  `id_configuracao_geral` int DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_agendamento_geracao_massa` (`id_geracao_massa`),
  KEY `fk_notificacoes_servicos` (`id_servico`),
  KEY `fk_notificacoes_massa_usuarios` (`id_usuario`),
  KEY `fk_agendamento_envio_notificacoes_gateway_notificacao_idx` (`id_gateway_notificacao`),
  KEY `agendamentos_status_push` (`status_push`),
  KEY `agendamentos_status_email` (`status_email`),
  KEY `agendamentos_status_gateway` (`status_gateway`),
  KEY `agendamentos_status_sms` (`status_telefone`),
  KEY `fk_agendamento_envio_notificacoes_configuracoes_gerais_idx` (`id_configuracao_geral`),
  CONSTRAINT `fk_agendamento_envio_notificacoes_configuracoes_gerais` FOREIGN KEY (`id_configuracao_geral`) REFERENCES `configuracoes_gerais` (`id`),
  CONSTRAINT `fk_agendamento_envio_notificacoes_gateway_notificacao` FOREIGN KEY (`id_gateway_notificacao`) REFERENCES `gateway_notificacao` (`id`),
  CONSTRAINT `fk_agendamento_geracao_massa` FOREIGN KEY (`id_geracao_massa`) REFERENCES `notificacoes_massa` (`id`),
  CONSTRAINT `fk_notificacoes_massa_usuarios` FOREIGN KEY (`id_usuario`) REFERENCES `usuarios` (`id`),
  CONSTRAINT `fk_notificacoes_servicos` FOREIGN KEY (`id_servico`) REFERENCES `servicos` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `agendamento_envio_notificacoes`
--

LOCK TABLES `agendamento_envio_notificacoes` WRITE;
/*!40000 ALTER TABLE `agendamento_envio_notificacoes` DISABLE KEYS */;
/*!40000 ALTER TABLE `agendamento_envio_notificacoes` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `agendamento_faturas_gerencianet`
--

DROP TABLE IF EXISTS `agendamento_faturas_gerencianet`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `agendamento_faturas_gerencianet` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_servico` int DEFAULT NULL,
  `id_geracao_faturas` int DEFAULT NULL,
  `id_usuario` int DEFAULT NULL,
  `data_inicio` datetime DEFAULT NULL,
  `data_fim` datetime DEFAULT NULL,
  `data` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `status` tinyint(1) NOT NULL DEFAULT '0',
  `data_processamento` datetime DEFAULT NULL,
  `sync` int DEFAULT '0',
  PRIMARY KEY (`id`),
  KEY `fk_agendamento_gerencianet_servico` (`id_servico`),
  KEY `fk_agendamento_gerencianet_geracao` (`id_geracao_faturas`),
  KEY `fk_agendamento_gerencianet_usuario` (`id_usuario`),
  CONSTRAINT `fk_agendamento_gerencianet_geracao` FOREIGN KEY (`id_geracao_faturas`) REFERENCES `geracao_faturas` (`id`),
  CONSTRAINT `fk_agendamento_gerencianet_servico` FOREIGN KEY (`id_servico`) REFERENCES `servicos` (`id`),
  CONSTRAINT `fk_agendamento_gerencianet_usuario` FOREIGN KEY (`id_usuario`) REFERENCES `usuarios` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `agendamento_faturas_gerencianet`
--

LOCK TABLES `agendamento_faturas_gerencianet` WRITE;
/*!40000 ALTER TABLE `agendamento_faturas_gerencianet` DISABLE KEYS */;
/*!40000 ALTER TABLE `agendamento_faturas_gerencianet` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `agendamento_lembretes_contas_receber`
--

DROP TABLE IF EXISTS `agendamento_lembretes_contas_receber`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `agendamento_lembretes_contas_receber` (
  `id` int NOT NULL AUTO_INCREMENT,
  `tipo` tinyint(1) DEFAULT NULL COMMENT '1 -> A vencer\n2 -> Vencida',
  `id_conta_receber` int DEFAULT NULL,
  `id_notificacao_email` int DEFAULT NULL,
  `id_notificacao_sms` int DEFAULT NULL,
  `id_notificacao_push` int DEFAULT NULL,
  `id_notificacao_gateway` int DEFAULT NULL,
  `dt_agendamento` datetime DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  KEY `fk_contas_receber_agendamento_lembretes_contas_receber_idx` (`id_conta_receber`),
  KEY `fk_agendamento_envio_notificacoes_idx` (`id_notificacao_email`),
  KEY `fk_agendamento_envio_notificacoes_idx1` (`id_notificacao_sms`),
  KEY `fk_agendamento_envio_notificacoes_idx2` (`id_notificacao_push`),
  KEY `fk_agendamento_envio_notificacoes_gateway_idx` (`id_notificacao_gateway`),
  CONSTRAINT `fk_agendamento_envio_notificacoes_email` FOREIGN KEY (`id_notificacao_email`) REFERENCES `agendamento_envio_notificacoes` (`id`),
  CONSTRAINT `fk_agendamento_envio_notificacoes_gateway` FOREIGN KEY (`id_notificacao_gateway`) REFERENCES `agendamento_envio_notificacoes` (`id`),
  CONSTRAINT `fk_agendamento_envio_notificacoes_push` FOREIGN KEY (`id_notificacao_push`) REFERENCES `agendamento_envio_notificacoes` (`id`),
  CONSTRAINT `fk_agendamento_envio_notificacoes_sms` FOREIGN KEY (`id_notificacao_sms`) REFERENCES `agendamento_envio_notificacoes` (`id`),
  CONSTRAINT `fk_contas_receber_agendamento_lembretes_contas_receber` FOREIGN KEY (`id_conta_receber`) REFERENCES `contas_receber` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `agendamento_lembretes_contas_receber`
--

LOCK TABLES `agendamento_lembretes_contas_receber` WRITE;
/*!40000 ALTER TABLE `agendamento_lembretes_contas_receber` DISABLE KEYS */;
/*!40000 ALTER TABLE `agendamento_lembretes_contas_receber` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `agendamentos`
--

DROP TABLE IF EXISTS `agendamentos`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `agendamentos` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_usuario` int DEFAULT NULL,
  `id_vendedor` int DEFAULT NULL,
  `id_endereco` int DEFAULT NULL,
  `numero` int DEFAULT NULL,
  `completo` varchar(100) DEFAULT NULL,
  `referencia` varchar(100) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `agendamentos`
--

LOCK TABLES `agendamentos` WRITE;
/*!40000 ALTER TABLE `agendamentos` DISABLE KEYS */;
/*!40000 ALTER TABLE `agendamentos` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `agendamentos_atualizar_sva`
--

DROP TABLE IF EXISTS `agendamentos_atualizar_sva`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `agendamentos_atualizar_sva` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_servico` int DEFAULT NULL,
  `id_integrador` int DEFAULT NULL,
  `pacotes` varchar(255) DEFAULT NULL,
  `operacao` varchar(45) DEFAULT 'adicionar',
  `data` datetime DEFAULT CURRENT_TIMESTAMP,
  `status` tinyint(1) DEFAULT '0',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `agendamentos_atualizar_sva`
--

LOCK TABLES `agendamentos_atualizar_sva` WRITE;
/*!40000 ALTER TABLE `agendamentos_atualizar_sva` DISABLE KEYS */;
/*!40000 ALTER TABLE `agendamentos_atualizar_sva` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `agendamentos_atualizar_velocidades`
--

DROP TABLE IF EXISTS `agendamentos_atualizar_velocidades`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `agendamentos_atualizar_velocidades` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_servico` int NOT NULL,
  `desconectar_cliente` tinyint NOT NULL DEFAULT '1',
  `data` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `status` tinyint NOT NULL DEFAULT '0',
  `id_migracao_servidor` int DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `agendamentos_atualizar_velocidades_servicos` (`id_servico`),
  CONSTRAINT `agendamentos_atualizar_velocidades_servicos` FOREIGN KEY (`id_servico`) REFERENCES `servicos` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `agendamentos_atualizar_velocidades`
--

LOCK TABLES `agendamentos_atualizar_velocidades` WRITE;
/*!40000 ALTER TABLE `agendamentos_atualizar_velocidades` DISABLE KEYS */;
/*!40000 ALTER TABLE `agendamentos_atualizar_velocidades` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `agendamentos_clientes_pendentes`
--

DROP TABLE IF EXISTS `agendamentos_clientes_pendentes`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `agendamentos_clientes_pendentes` (
  `id` int NOT NULL AUTO_INCREMENT,
  `sql_conteudo` longtext,
  `data` datetime DEFAULT CURRENT_TIMESTAMP,
  `id_usuario` int DEFAULT NULL,
  `status` tinyint(1) DEFAULT '0',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `agendamentos_clientes_pendentes`
--

LOCK TABLES `agendamentos_clientes_pendentes` WRITE;
/*!40000 ALTER TABLE `agendamentos_clientes_pendentes` DISABLE KEYS */;
/*!40000 ALTER TABLE `agendamentos_clientes_pendentes` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `agendamentos_geracao_notas`
--

DROP TABLE IF EXISTS `agendamentos_geracao_notas`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `agendamentos_geracao_notas` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_servico` int DEFAULT NULL,
  `data` datetime DEFAULT CURRENT_TIMESTAMP,
  `status` tinyint(1) DEFAULT '1',
  `id_plano` int DEFAULT NULL,
  `valor` float(10,2) DEFAULT '0.00',
  `notas` varchar(500) DEFAULT NULL,
  `id_geracao_massa` int DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_id_servico_nota_idx` (`id_servico`),
  KEY `fk_id_plano_nota_idx` (`id_plano`),
  CONSTRAINT `fk_id_plano_nota` FOREIGN KEY (`id_plano`) REFERENCES `planos` (`id`),
  CONSTRAINT `fk_id_servico_nota` FOREIGN KEY (`id_servico`) REFERENCES `servicos` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `agendamentos_geracao_notas`
--

LOCK TABLES `agendamentos_geracao_notas` WRITE;
/*!40000 ALTER TABLE `agendamentos_geracao_notas` DISABLE KEYS */;
/*!40000 ALTER TABLE `agendamentos_geracao_notas` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `agendamentos_servicos_renovacao`
--

DROP TABLE IF EXISTS `agendamentos_servicos_renovacao`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `agendamentos_servicos_renovacao` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_servico` int DEFAULT NULL,
  `id_promocao` int DEFAULT NULL,
  `data` datetime DEFAULT CURRENT_TIMESTAMP,
  `status` varchar(45) DEFAULT '0',
  PRIMARY KEY (`id`),
  KEY `fk_servicos_renovacao_servico_idx` (`id_servico`),
  KEY `fk_servicos_renovacao_promocao_idx` (`id_promocao`),
  CONSTRAINT `fk_servicos_renovacao_promocao` FOREIGN KEY (`id_promocao`) REFERENCES `promocoes` (`id`),
  CONSTRAINT `fk_servicos_renovacao_servico` FOREIGN KEY (`id_servico`) REFERENCES `servicos` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `agendamentos_servicos_renovacao`
--

LOCK TABLES `agendamentos_servicos_renovacao` WRITE;
/*!40000 ALTER TABLE `agendamentos_servicos_renovacao` DISABLE KEYS */;
/*!40000 ALTER TABLE `agendamentos_servicos_renovacao` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `agendamentos_vlans_olts`
--

DROP TABLE IF EXISTS `agendamentos_vlans_olts`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `agendamentos_vlans_olts` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_pon` int DEFAULT NULL,
  `data` datetime DEFAULT CURRENT_TIMESTAMP,
  `status` tinyint(1) DEFAULT '0',
  PRIMARY KEY (`id`),
  KEY `fk_agendamentos_vlan_pon_idx` (`id_pon`),
  CONSTRAINT `fk_agendamentos_vlan_pon` FOREIGN KEY (`id_pon`) REFERENCES `pons` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `agendamentos_vlans_olts`
--

LOCK TABLES `agendamentos_vlans_olts` WRITE;
/*!40000 ALTER TABLE `agendamentos_vlans_olts` DISABLE KEYS */;
/*!40000 ALTER TABLE `agendamentos_vlans_olts` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `almoxarifados`
--

DROP TABLE IF EXISTS `almoxarifados`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `almoxarifados` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nome` varchar(200) NOT NULL,
  `status` tinyint(1) NOT NULL DEFAULT '1',
  `principal` tinyint(1) DEFAULT '0',
  `id_filial` int DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_almoxarifados_filiais_idx` (`id_filial`),
  CONSTRAINT `fk_almoxarifados_filiais` FOREIGN KEY (`id_filial`) REFERENCES `filiais` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `almoxarifados`
--

LOCK TABLES `almoxarifados` WRITE;
/*!40000 ALTER TABLE `almoxarifados` DISABLE KEYS */;
INSERT INTO `almoxarifados` VALUES (1,'[1] - SiimCloud',1,1,1);
/*!40000 ALTER TABLE `almoxarifados` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `alteracoes_situacao_servicos_automaticas`
--

DROP TABLE IF EXISTS `alteracoes_situacao_servicos_automaticas`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `alteracoes_situacao_servicos_automaticas` (
  `id` int NOT NULL AUTO_INCREMENT,
  `tipo_alteracao` tinyint(1) DEFAULT '0' COMMENT '0 -> bloqueio\n1 -> alteração por inadimplencia\n2 -> Reversao de operacao',
  `data` datetime DEFAULT CURRENT_TIMESTAMP,
  `id_usuario` int DEFAULT NULL,
  `motivo` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `alteracoes_situacao_servicos_automaticas`
--

LOCK TABLES `alteracoes_situacao_servicos_automaticas` WRITE;
/*!40000 ALTER TABLE `alteracoes_situacao_servicos_automaticas` DISABLE KEYS */;
/*!40000 ALTER TABLE `alteracoes_situacao_servicos_automaticas` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `arquivos_clientes`
--

DROP TABLE IF EXISTS `arquivos_clientes`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `arquivos_clientes` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_servico` int DEFAULT NULL,
  `nome` varchar(255) NOT NULL,
  `observacoes` longtext,
  `data` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `descricao` text,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `arquivos_clientes`
--

LOCK TABLES `arquivos_clientes` WRITE;
/*!40000 ALTER TABLE `arquivos_clientes` DISABLE KEYS */;
/*!40000 ALTER TABLE `arquivos_clientes` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `asaas_pix_transacoes`
--

DROP TABLE IF EXISTS `asaas_pix_transacoes`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `asaas_pix_transacoes` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_conta_receber` int DEFAULT NULL,
  `json` longtext,
  `json_detalhe` longtext,
  `encodedImage` longtext,
  `payload` varchar(255) DEFAULT NULL,
  `type` varchar(255) DEFAULT NULL,
  `pixKey` varchar(255) DEFAULT NULL,
  `conciliationIdentifier` varchar(255) DEFAULT NULL,
  `endToEndIdentifier` varchar(255) DEFAULT NULL,
  `dueDate` varchar(255) DEFAULT NULL,
  `expirationDate` varchar(255) DEFAULT NULL,
  `totalValue` varchar(255) DEFAULT NULL,
  `status` varchar(255) DEFAULT NULL,
  `dt_cadastro` datetime DEFAULT CURRENT_TIMESTAMP,
  `id_retorno_pix` int DEFAULT NULL,
  `pixTransaction` varchar(255) DEFAULT NULL,
  `paymentId` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`) USING BTREE,
  KEY `fk_asaas_pix_transacoes_contas_receber_idx` (`id_conta_receber`) USING BTREE,
  KEY `fk_asaas_pix_transacoes_retorno_pix_idx` (`id_retorno_pix`),
  CONSTRAINT `fk_asaas_pix_transacoes_contas_receber` FOREIGN KEY (`id_conta_receber`) REFERENCES `contas_receber` (`id`),
  CONSTRAINT `fk_asaas_pix_transacoes_retorno_pix` FOREIGN KEY (`id_retorno_pix`) REFERENCES `retornos_pix` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `asaas_pix_transacoes`
--

LOCK TABLES `asaas_pix_transacoes` WRITE;
/*!40000 ALTER TABLE `asaas_pix_transacoes` DISABLE KEYS */;
/*!40000 ALTER TABLE `asaas_pix_transacoes` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `atendimentos`
--

DROP TABLE IF EXISTS `atendimentos`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `atendimentos` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_contrato` int DEFAULT NULL,
  `id_contato` int DEFAULT NULL,
  `link_arquivo_gravacao` varchar(255) DEFAULT NULL,
  `nome_arquivo_gravacao` varchar(255) DEFAULT NULL,
  `id_usuario_abertura` int NOT NULL,
  `id_tipo_abertura_chamado` int DEFAULT NULL,
  `id_pre_cadastro` int DEFAULT NULL,
  `dt_abertura` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `id_usuario_fechado` int DEFAULT NULL,
  `dt_fechado` datetime DEFAULT NULL,
  `situacao` int NOT NULL,
  `nome_contato` varchar(255) DEFAULT NULL,
  `telefone_contato` varchar(100) DEFAULT NULL,
  `id_filial` int DEFAULT '1',
  `relato_cliente` text,
  `descricao_finalizar` text,
  `id_categoria_atendimento` int DEFAULT NULL,
  `id_origem_contato` int DEFAULT NULL,
  `id_departamento_zapline` int DEFAULT NULL,
  `id_lead` int DEFAULT NULL,
  `converter_lead` int DEFAULT '0',
  `id_sla` int DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_id_tipo_abertura_chamado` (`id_tipo_abertura_chamado`),
  KEY `fk_id_pre_cadastro` (`id_pre_cadastro`),
  KEY `fk_id_contrato` (`id_contrato`),
  KEY `fk_atendimentos_atendimento_idx` (`id_filial`),
  KEY `fk_origem_contato_atendimento_idx` (`id_origem_contato`),
  KEY `fk_atendimento_departamento_idx` (`id_departamento_zapline`),
  KEY `fk_atendimento_lead_idx` (`id_lead`),
  KEY `indice_filial` (`id_filial`),
  KEY `dt_abertura_INDICE` (`dt_abertura`),
  KEY `fk_atendimentos_sla_idx` (`id_sla`),
  CONSTRAINT `fk_atendimento_departamento` FOREIGN KEY (`id_departamento_zapline`) REFERENCES `departamentos` (`id`),
  CONSTRAINT `fk_atendimento_lead` FOREIGN KEY (`id_lead`) REFERENCES `lead_crm` (`id`),
  CONSTRAINT `fk_atendimentos_filiais` FOREIGN KEY (`id_filial`) REFERENCES `filiais` (`id`),
  CONSTRAINT `fk_atendimentos_sla` FOREIGN KEY (`id_sla`) REFERENCES `slas` (`id`),
  CONSTRAINT `fk_id_contrato` FOREIGN KEY (`id_contrato`) REFERENCES `contratos` (`id`),
  CONSTRAINT `fk_id_pre_cadastro` FOREIGN KEY (`id_pre_cadastro`) REFERENCES `pre_cadastros` (`id`),
  CONSTRAINT `fk_id_tipo_abertura_chamado` FOREIGN KEY (`id_tipo_abertura_chamado`) REFERENCES `tipo_abertura_chamado` (`id`),
  CONSTRAINT `fk_origem_contato_atendimento` FOREIGN KEY (`id_origem_contato`) REFERENCES `origem_contatos` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `atendimentos`
--

LOCK TABLES `atendimentos` WRITE;
/*!40000 ALTER TABLE `atendimentos` DISABLE KEYS */;
/*!40000 ALTER TABLE `atendimentos` ENABLE KEYS */;
UNLOCK TABLES;
/*!40103 SET TIME_ZONE=@OLD_TIME_ZONE */;

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */;

-- Dump completed on 2023-09-23 16:00:16

