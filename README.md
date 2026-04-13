# BANCO-DE-DADOS
CREATE DATABASE  IF NOT EXISTS `basefinanceira` /*!40100 DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci */ /*!80016 DEFAULT ENCRYPTION='N' */;
USE `basefinanceira`;
-- MySQL dump 10.13  Distrib 8.0.38, for Win64 (x86_64)
--
-- Host: 127.0.0.1    Database: basefinanceira
-- ------------------------------------------------------
-- Server version	8.0.39

/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!50503 SET NAMES utf8 */;
/*!40103 SET @OLD_TIME_ZONE=@@TIME_ZONE */;
/*!40103 SET TIME_ZONE='+00:00' */;
/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;

--
-- Table structure for table `destinatario`
--

DROP TABLE IF EXISTS `destinatario`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `destinatario` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nome_razao_social` varchar(255) NOT NULL,
  `cpf_cnpj` char(14) NOT NULL,
  `inscricao_estadual` varchar(50) DEFAULT NULL,
  `endereco` varchar(400) DEFAULT NULL,
  `numero` varchar(20) DEFAULT NULL,
  `complemento` varchar(200) DEFAULT NULL,
  `bairro` varchar(150) DEFAULT NULL,
  `municipio` varchar(150) DEFAULT NULL,
  `uf` char(2) DEFAULT NULL,
  `cep` char(8) DEFAULT NULL,
  `telefone` varchar(30) DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  `updated_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  KEY `cpf_cnpj` (`cpf_cnpj`)
) ENGINE=InnoDB AUTO_INCREMENT=6 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `destinatario`
--

LOCK TABLES `destinatario` WRITE;
/*!40000 ALTER TABLE `destinatario` DISABLE KEYS */;
INSERT INTO `destinatario` VALUES (1,'Fagner Fernandes Douetts','054125****3',NULL,'Quadra 2 Conjunto A-1, SN-Bloco C AP 407',NULL,NULL,'Sobradinho','Brasilia','DF','73015101',NULL,'2025-11-14 00:20:27','2025-11-14 00:20:27'),(2,'Fagner Fernandes Douetts','054125****3',NULL,'QUADRA 1 RUA C','6',NULL,'Setor Industrial','Brasilia','DF','73020021',NULL,'2025-11-14 00:20:27','2025-11-14 00:20:27'),(3,'FAGNER FERNANDES DOUETTS','054125****3',NULL,'QUADRA 2 CONJUNTO A-1,0-BLOCO C AP 407',NULL,NULL,'SOBRADINHO','BRASILIA','DF','73015101',NULL,'2025-11-14 00:20:27','2025-11-14 00:20:27'),(4,'Fagner Fernandes Douetts','054125****3',NULL,'SETOR COLINA NOVA DIGUINEIA II CONJUNTO E 01',NULL,NULL,'Nova Colina sobradinho','Braslia','DF','73270100',NULL,'2025-11-14 00:24:26','2025-11-14 00:24:26'),(5,'Fagner Fernandes Douetts','054125****3',NULL,'Quadra 2 Conjunto B4, 25ap 103',NULL,NULL,'Sobradinho','Brasilia','DF','73020024','61982975422','2025-11-14 00:28:31','2025-11-14 00:28:31');
/*!40000 ALTER TABLE `destinatario` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `emitente`
--

DROP TABLE IF EXISTS `emitente`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `emitente` (
  `id` int NOT NULL AUTO_INCREMENT,
  `razao_social` varchar(255) NOT NULL,
  `nome_fantasia` varchar(255) DEFAULT NULL,
  `cnpj` char(14) NOT NULL,
  `inscricao_estadual` varchar(50) DEFAULT NULL,
  `inscricao_municipal` varchar(50) DEFAULT NULL,
  `endereco` varchar(400) DEFAULT NULL,
  `numero` varchar(20) DEFAULT NULL,
  `complemento` varchar(200) DEFAULT NULL,
  `bairro` varchar(150) DEFAULT NULL,
  `municipio` varchar(150) DEFAULT NULL,
  `uf` char(2) DEFAULT NULL,
  `cep` char(8) DEFAULT NULL,
  `telefone` varchar(30) DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  `updated_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  UNIQUE KEY `cnpj` (`cnpj`)
) ENGINE=InnoDB AUTO_INCREMENT=12 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `emitente`
--

LOCK TABLES `emitente` WRITE;
/*!40000 ALTER TABLE `emitente` DISABLE KEYS */;
INSERT INTO `emitente` VALUES (1,'LECA METAIS LTDA',NULL,'14908713000162','9065462211',NULL,'Rua Pedro Arnaldo Maschietto','45',NULL,'PARQUE INDUSTRIAL IV','Loanda','PR','87900000','0044999215988','2025-11-14 00:20:27','2025-11-14 00:20:27'),(2,'TSY COMERCIO DE ELETROELETRONICOS LTDA',NULL,'20777802000110','143785766117',NULL,'Avenida Guapira','596',NULL,'Tucuruvi','Sao Paulo','SP','02265001','001122091848','2025-11-14 00:20:27','2025-11-14 00:20:27'),(3,'SEVEN GLASS STORE LTDA',NULL,'25273443000187','286832571112',NULL,'AV FAGUNDES DE OLIVEIRA','1200',NULL,'PIRAPORINHA','DIADEMA','SP','09950615','11955778825','2025-11-14 00:20:27','2025-11-14 00:20:27'),(4,'ELIZAZ VARIEDADES LTDA',NULL,'58910140000187','152352380111',NULL,'SEN QUEIROS','360',NULL,'CENTRO','So Paulo','SP','01026000',NULL,'2025-11-14 00:24:26','2025-11-14 00:24:26'),(5,'CASA DALONSO LOJA DE DEPARTAMENTOS LTDA',NULL,'37762181000101','129285500117',NULL,'Rua Severa','227',NULL,'Vila Maria Baixa','Sao Paulo','SP','02111000','11983094347','2025-11-14 00:24:26','2025-11-14 00:24:26'),(6,'VENT MAX PRESENTES LTDA',NULL,'58909952000102','152352317115',NULL,'COMEN AFONSO KHERLAKIAN','79',NULL,'CENTRO','So Paulo','SP','01023903',NULL,'2025-11-14 00:24:26','2025-11-14 00:24:26'),(7,'WEB ATACADO E VAREJO LTDA',NULL,'46931819000173','136354328119',NULL,'Rua Kampala','35',NULL,'Jardim America da Penha','Sao Paulo','SP','03704015',NULL,'2025-11-14 00:26:43','2025-11-14 00:26:43'),(8,'BWINX COMERCIAL LTDA',NULL,'20717387000109','257420967',NULL,'R Rodolfo Hansen','41',NULL,'Passo Manso','Blumenau','SC','89032530','004732853800','2025-11-14 00:26:43','2025-11-14 00:26:43'),(9,'FRIGELAR COMERCIO E INDUSTRIA LTDA',NULL,'92660406005269','0010228811139',NULL,'ROD FERNAO DIAS','S/N',NULL,' KM 935 PARTE A-DOS PESSEGUEIROS','Extrema','MG','37646905',NULL,'2025-11-14 00:30:39','2025-11-14 00:30:39'),(10,'JUN COMERCIO DE VARIEDADES E ACESSORIOS ELETRONICOS LTDA',NULL,'55249174000184','137469388112',NULL,'R Sampson','72',NULL,'Bras','Sao Paulo','SP','03013040',NULL,'2025-11-14 00:30:39','2025-11-14 00:30:39'),(11,'PS IMPORTS E-COMMERCE LTDA',NULL,'37865863000131',NULL,NULL,'Rua dos Campineiros','284',NULL,'Mooca','Sao Paulo','SP','03167020',NULL,'2025-11-14 00:30:39','2025-11-14 00:30:39');
/*!40000 ALTER TABLE `emitente` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `nf_imposto`
--

DROP TABLE IF EXISTS `nf_imposto`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `nf_imposto` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nota_id` int DEFAULT NULL,
  `item_id` int DEFAULT NULL,
  `tipo_imposto` varchar(50) DEFAULT NULL,
  `base_calculo` decimal(18,2) DEFAULT NULL,
  `aliquota` decimal(6,4) DEFAULT NULL,
  `valor` decimal(18,2) DEFAULT NULL,
  `info` json DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  KEY `nota_id` (`nota_id`),
  KEY `item_id` (`item_id`),
  CONSTRAINT `nf_imposto_ibfk_1` FOREIGN KEY (`nota_id`) REFERENCES `nota_fiscal` (`id`) ON DELETE CASCADE,
  CONSTRAINT `nf_imposto_ibfk_2` FOREIGN KEY (`item_id`) REFERENCES `nf_item` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=33 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `nf_imposto`
--

LOCK TABLES `nf_imposto` WRITE;
/*!40000 ALTER TABLE `nf_imposto` DISABLE KEYS */;
INSERT INTO `nf_imposto` VALUES (1,1,1,'ICMS',0.00,0.0000,0.00,NULL,'2025-11-14 00:20:27'),(2,1,1,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:20:27'),(3,1,2,'ICMS',0.00,0.0000,0.00,NULL,'2025-11-14 00:20:27'),(4,1,2,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:20:27'),(5,1,3,'ICMS',0.00,0.0000,0.00,NULL,'2025-11-14 00:20:27'),(6,1,3,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:20:27'),(7,2,4,'ICMS',476.26,7.0000,33.34,NULL,'2025-11-14 00:20:27'),(8,2,4,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:20:27'),(9,2,5,'ICMS',91.33,7.0000,6.39,NULL,'2025-11-14 00:20:27'),(10,2,5,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:20:27'),(11,3,6,'ICMS',582.00,4.0000,23.28,NULL,'2025-11-14 00:20:27'),(12,3,6,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:20:27'),(13,4,7,'ICMS',0.00,0.0000,0.00,NULL,'2025-11-14 00:24:26'),(14,4,7,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:24:26'),(15,5,8,'ICMS',132.54,4.0000,5.30,NULL,'2025-11-14 00:24:26'),(16,5,8,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:24:26'),(17,6,9,'ICMS',0.00,0.0000,0.00,NULL,'2025-11-14 00:24:26'),(18,6,9,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:24:26'),(19,6,10,'ICMS',0.00,0.0000,0.00,NULL,'2025-11-14 00:24:26'),(20,6,10,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:24:26'),(21,6,11,'ICMS',0.00,0.0000,0.00,NULL,'2025-11-14 00:24:26'),(22,6,11,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:24:26'),(23,7,12,'ICMS',0.00,0.0000,0.00,NULL,'2025-11-14 00:26:43'),(24,7,12,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:26:43'),(25,8,13,'ICMS',106.40,4.0000,4.26,NULL,'2025-11-14 00:26:43'),(26,8,13,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:26:43'),(27,9,14,'ICMS',1180.44,4.0000,47.22,NULL,'2025-11-14 00:30:39'),(28,9,14,'IPI',NULL,3.2500,37.16,NULL,'2025-11-14 00:30:39'),(29,10,15,'ICMS',0.00,0.0000,0.00,NULL,'2025-11-14 00:30:39'),(30,10,15,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:30:39'),(31,11,16,'ICMS',103.00,4.0000,4.12,NULL,'2025-11-14 00:30:39'),(32,11,16,'IPI',NULL,0.0000,0.00,NULL,'2025-11-14 00:30:39');
/*!40000 ALTER TABLE `nf_imposto` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `nf_informacoes_adicionais`
--

DROP TABLE IF EXISTS `nf_informacoes_adicionais`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `nf_informacoes_adicionais` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nota_id` int NOT NULL,
  `informacoes_complementares` text,
  `valor_aprox_tributos` decimal(18,2) DEFAULT NULL,
  `difal_destino` decimal(18,2) DEFAULT NULL,
  `difal_origem` decimal(18,2) DEFAULT NULL,
  `fcp` decimal(18,2) DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  UNIQUE KEY `nota_id` (`nota_id`),
  CONSTRAINT `nf_informacoes_adicionais_ibfk_1` FOREIGN KEY (`nota_id`) REFERENCES `nota_fiscal` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=10 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `nf_informacoes_adicionais`
--

LOCK TABLES `nf_informacoes_adicionais` WRITE;
/*!40000 ALTER TABLE `nf_informacoes_adicionais` DISABLE KEYS */;
INSERT INTO `nf_informacoes_adicionais` VALUES (1,1,'Mercadoria enviada diretamente do deposito do Operador Logistico EBAZAR.COM.BR LTDA, estabelecido AREA ESP AEROPORTO, LGO SUL, UC4047, S/N, S/N, Bairro LAGO SUL, Brasilia, DF, CEP 71608900, inscrito no CNPJ/MF sob o n 03007331019918, Inscricao Estadual n 0811964700600, conforme Ajuste SINIEF n 35/22 e Decreto N 44.181, de 30 de Janeiro de 2023 Emitido por ME/EPP optante do Simples Nacional.',31.06,NULL,NULL,NULL,'2025-11-14 00:20:27'),(2,2,'Enviado diretamente do deposito temporario operador logistico: EBAZAR.COM.BR LTDA, Cnpj: 03007331007901, Inscricao Estadual: 241174910115 saindo do endereco: Av. Dr. Antonio Joao Abdalla, Numero: 3333, Complemento:, Bairro: Empresarial Colina, Cidade: Cajamar, Cep: 07750901, Estado: SP, Pais: BR. Nota fiscal de retorno simbolico n 702752, emitida em 15/10/2025, serie 3, nos termos da Portaria CAT 31/2019 Valores totais do ICMS Interestadual: DIFAL da UF destino R$81,48 + FCP R$0,00; DIFAL da UF Origem R$0,00.',202.43,81.48,0.00,0.00,'2025-11-14 00:20:27'),(3,3,'#VENDEDOR: MERCADO LIVRE NOSSO PEDIDO: 1172477 #Origem: ML SEVEN GLASS - Rastreamento: null - Integracao: 2000012521657512-EntregalD: 45275723686;',NULL,NULL,NULL,NULL,'2025-11-14 00:20:27'),(4,4,'Conf. Lei 12.741/2012 Tributao aprox. R$6.54 (5.0%) Federal e R$6.54 (5.0%) Estadual /',13.08,NULL,NULL,NULL,'2025-11-14 00:24:26'),(5,5,'Enviado diretamente do deposito temporario operador logistico: EBAZAR.COM.BR LTDA, Cnpj: 03007331012158, Inscricao Estadual: 312210513110 saindo do endereco: Rod. Pres. Tancredo de Almeida Neves, Numero: 45, Complemento:, Bairro: Parque Santa Delfa, Cidade: Franco da Rocha, Cep: 07809105, Estado: SP, Pais: BR. Nota fiscal de retorno simbolico n 329893, emitida em 07/08/2025, serie 2, nos termos da Portaria CAT 31/2019 Valores totais do ICMS Interestadual: DIFAL da UF destino R$18,56 + FCP R$0,00; DIFAL da UF Origem R$0,00.',58.53,18.56,0.00,0.00,'2025-11-14 00:24:26'),(6,6,'Conf. Lei 12.741/2012 Tributao aprox. R$32.92 (17.0%) Federal e R$34.86 (18.0%) Estadual - Fonte IBPT/',67.78,NULL,NULL,NULL,'2025-11-14 00:24:26'),(7,7,'Mercadoria enviada diretamente do deposito do Operador Logistico EBAZAR.COM.BR LTDA, estabelecido AREA ESP AEROPORTO, LGO SUL, UC4047, S/N, S/N, Bairro LAGO SUL, Brasilia, DF, CEP 71608900, inscrito no CNPJ/MF sob o n 03007331019918, Inscricao Estadual n 0811964700600, conforme Ajuste SINIEF n 35/22 e Decreto N 44.181, de 30 de Janeiro de 2023. Emitido por ME/EPP optante do Simples Nacional.',23.16,NULL,NULL,NULL,'2025-11-14 00:26:43'),(8,8,'Enviado diretamente do deposito temporario operador logistico: EBAZAR.COM.BR LTDA, Cnpj: 03007331012077, Inscricao Estadual: 261755994, saindo do endereco: Av. Papenborg, Numero: S/N, Complemento:, Bairro: Guaporanga, Cidade: Governador Celso Ramos, Cep: 88190000, Estado: SC, Pais: BR. Nota fiscal de retorno simbolico n 263963, emitida em 27/04/2025, serie 2.',27.65,14.90,NULL,NULL,'2025-11-14 00:26:43'),(9,9,NULL,444.60,NULL,NULL,NULL,'2025-11-14 00:30:39');
/*!40000 ALTER TABLE `nf_informacoes_adicionais` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `nf_item`
--

DROP TABLE IF EXISTS `nf_item`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `nf_item` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nota_id` int NOT NULL,
  `numero_item` int NOT NULL,
  `codigo` varchar(100) DEFAULT NULL,
  `descricao` text,
  `ncm_sh` varchar(20) DEFAULT NULL,
  `cest` varchar(20) DEFAULT NULL,
  `cst` varchar(20) DEFAULT NULL,
  `csosn` varchar(20) DEFAULT NULL,
  `cfop` varchar(10) DEFAULT NULL,
  `unidade` varchar(20) DEFAULT NULL,
  `quantidade` decimal(18,6) DEFAULT '0.000000',
  `valor_unitario` decimal(18,6) DEFAULT '0.000000',
  `valor_total` decimal(18,2) DEFAULT '0.00',
  `informacoes_adicionais_item` text,
  `created_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  UNIQUE KEY `ux_nf_item_nota_numeroitem` (`nota_id`,`numero_item`),
  CONSTRAINT `nf_item_ibfk_1` FOREIGN KEY (`nota_id`) REFERENCES `nota_fiscal` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=17 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `nf_item`
--

LOCK TABLES `nf_item` WRITE;
/*!40000 ALTER TABLE `nf_item` DISABLE KEYS */;
INSERT INTO `nf_item` VALUES (1,1,1,'MLB4959130310 181227924','Chuveiro Ducha Quadrado 20x20-PRETO','84818019',NULL,NULL,'0102','6106','UN',1.000000,73.450000,73.45,NULL,'2025-11-14 00:20:27'),(2,1,2,'MLB4959130310 1','Conversor de Registro Docol para Deca','84819010',NULL,NULL,'0102','6105','UN',1.000000,8.170000,8.17,NULL,'2025-11-14 00:20:27'),(3,1,3,'MLB4959130310','Acabamento de Registro Quadrado 1/2 3/4- PRETO','84818019',NULL,NULL,'0102','6106','UN',1.000000,16.340000,16.34,NULL,'2025-11-14 00:20:27'),(4,2,1,'35698','CJMOV DZ ATTO 36 NITRO 127V/220V 400KG','84798999',NULL,'020',NULL,'6106','UN',1.000000,649.380000,649.38,NULL,'2025-11-14 00:20:27'),(5,2,2,'852','ROSSI BARRA DENTADA LEVE 0.5M X 2 SERIE R','84839000',NULL,'000',NULL,'6106','UN',5.000000,18.266000,91.33,NULL,'2025-11-14 00:20:27'),(6,3,1,'100100.10','NEUHAUS CONJ PANELAS 10 PECAS REV CERAMICO ANTIAD. E ACES. SILICONE-D-','76151000',NULL,'200',NULL,'6108','UN',1.000000,582.000000,582.00,NULL,'2025-11-14 00:20:27'),(7,4,1,'MLB5030412402','Fita De Led Cob 18wm 480 Leds Rolo 10 Metros Brancoquent Direto Na Rede-220V, Brancoquente,','94053100',NULL,NULL,'0102','6108','UN',1.000000,130.900000,130.90,NULL,'2025-11-14 00:24:26'),(8,5,1,'BM-F1102','Cesto Roupa Com Tampa Retangular Alca Bambu Multiuso Forrado','46021100',NULL,'200',NULL,'6106','UNID',2.000000,66.270000,132.54,NULL,'2025-11-14 00:24:26'),(9,6,1,'MLB3836389281 12V24V','Kit 10 Conector Emenda L Acrlica Para Fita De Led 8mm-12V24V','94059200',NULL,NULL,'0102','6108','UN',1.000000,39.900000,39.90,NULL,'2025-11-14 00:24:26'),(10,6,2,'MLB5030412402 Brancoquent','Fita De Led Cob 18wm 480 Leds Rolo 10 Metros Direto Na Rede-Brancoquente 220V,','94053100',NULL,NULL,'0102','6108','UN',1.000000,128.900000,128.90,NULL,'2025-11-14 00:24:26'),(11,6,3,'MLB5277915180','Kit 5 Conectores Encaixe Rabicho 2 Vias Fita Led 8mm','94059200',NULL,NULL,'0102','6108','UN',1.000000,24.900000,24.90,NULL,'2025-11-14 00:24:26'),(12,7,1,'hx7250-p','bolsa termica','42022220',NULL,NULL,'2102','6106','UNID',1.000000,33.820000,33.82,NULL,'2025-11-14 00:26:43'),(13,8,1,'TORTOM3PTOP','Torre com 3 tomadas Preto e Prata Renna','85369090',NULL,'200',NULL,'6106','UNID',1.000000,106.400000,106.40,NULL,'2025-11-14 00:26:43'),(14,9,1,'B170018','COOKTOP DE INDUCAO FREEZONE QUATRO BOCAS PRETO 7200W EOS ECI04EPF 220V-','85166000',NULL,'100',NULL,'6108','Pc',1.000000,1099.430000,1099.43,NULL,'2025-11-14 00:30:39'),(15,10,1,'2-TF card-32G','Kit 2 Cartao Memoria Micro 32gb Genai Original Cameras Wifi','85235110',NULL,NULL,'2102','6106','UNID',2.000000,32.395000,64.79,NULL,'2025-11-14 00:30:39'),(16,11,1,'Kit2 A8','Kit 2camera ip Icsee Prova D agua Infravermelho Externa Wifi Ps Imports','85258019',NULL,'200',NULL,'6106','UNID',1.000000,103.000000,103.00,NULL,'2025-11-14 00:30:39');
/*!40000 ALTER TABLE `nf_item` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `nf_pagamento`
--

DROP TABLE IF EXISTS `nf_pagamento`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `nf_pagamento` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nota_id` int NOT NULL,
  `forma_pagamento` varchar(80) DEFAULT NULL,
  `valor` decimal(18,2) DEFAULT NULL,
  `data_vencimento` date DEFAULT NULL,
  `identificador` varchar(200) DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  KEY `nota_id` (`nota_id`),
  CONSTRAINT `nf_pagamento_ibfk_1` FOREIGN KEY (`nota_id`) REFERENCES `nota_fiscal` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `nf_pagamento`
--

LOCK TABLES `nf_pagamento` WRITE;
/*!40000 ALTER TABLE `nf_pagamento` DISABLE KEYS */;
/*!40000 ALTER TABLE `nf_pagamento` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `nf_recebimento`
--

DROP TABLE IF EXISTS `nf_recebimento`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `nf_recebimento` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nota_id` int NOT NULL,
  `data_recebimento` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  `nome_recebedor` varchar(255) DEFAULT NULL,
  `assinatura_recebedor` blob,
  `observacao` text,
  PRIMARY KEY (`id`),
  KEY `nota_id` (`nota_id`),
  CONSTRAINT `nf_recebimento_ibfk_1` FOREIGN KEY (`nota_id`) REFERENCES `nota_fiscal` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `nf_recebimento`
--

LOCK TABLES `nf_recebimento` WRITE;
/*!40000 ALTER TABLE `nf_recebimento` DISABLE KEYS */;
/*!40000 ALTER TABLE `nf_recebimento` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `nf_totais`
--

DROP TABLE IF EXISTS `nf_totais`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `nf_totais` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nota_id` int NOT NULL,
  `base_icms` decimal(18,2) DEFAULT NULL,
  `valor_icms` decimal(18,2) DEFAULT NULL,
  `base_icms_st` decimal(18,2) DEFAULT NULL,
  `valor_icms_st` decimal(18,2) DEFAULT NULL,
  `valor_produtos` decimal(18,2) DEFAULT NULL,
  `valor_frete` decimal(18,2) DEFAULT NULL,
  `valor_seguro` decimal(18,2) DEFAULT NULL,
  `desconto` decimal(18,2) DEFAULT NULL,
  `outras_despesas` decimal(18,2) DEFAULT NULL,
  `valor_ipi` decimal(18,2) DEFAULT NULL,
  `valor_pis` decimal(18,2) DEFAULT NULL,
  `valor_cofins` decimal(18,2) DEFAULT NULL,
  `valor_total_nf` decimal(18,2) DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  KEY `nota_id` (`nota_id`),
  CONSTRAINT `nf_totais_ibfk_1` FOREIGN KEY (`nota_id`) REFERENCES `nota_fiscal` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=12 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `nf_totais`
--

LOCK TABLES `nf_totais` WRITE;
/*!40000 ALTER TABLE `nf_totais` DISABLE KEYS */;
INSERT INTO `nf_totais` VALUES (1,1,0.00,0.00,0.00,0.00,97.96,0.00,0.00,0.00,0.00,0.00,NULL,NULL,97.96,'2025-11-14 00:20:27'),(2,2,567.59,39.73,0.00,0.00,740.71,0.00,0.00,0.00,0.00,0.00,NULL,NULL,740.71,'2025-11-14 00:20:27'),(3,3,582.00,23.28,0.00,0.00,582.00,0.00,0.00,0.00,0.00,0.00,NULL,NULL,582.00,'2025-11-14 00:20:27'),(4,4,0.00,0.00,0.00,0.00,130.90,0.00,0.00,0.00,0.00,0.00,NULL,NULL,130.90,'2025-11-14 00:24:26'),(5,5,132.54,5.30,0.00,0.00,132.54,0.00,0.00,0.00,0.00,0.00,NULL,NULL,132.54,'2025-11-14 00:24:26'),(6,6,0.00,0.00,0.00,0.00,193.70,0.00,0.00,0.00,0.00,0.00,NULL,NULL,193.70,'2025-11-14 00:24:26'),(7,7,0.00,0.00,0.00,0.00,33.82,0.00,0.00,0.00,0.00,0.00,NULL,NULL,33.82,'2025-11-14 00:26:43'),(8,8,106.40,4.26,0.00,0.00,106.40,0.00,0.00,0.00,0.00,0.00,NULL,NULL,106.40,'2025-11-14 00:26:43'),(9,9,1180.44,47.22,NULL,NULL,1099.43,NULL,NULL,NULL,NULL,37.16,NULL,NULL,1136.59,'2025-11-14 00:30:39'),(10,10,0.00,0.00,NULL,NULL,64.79,NULL,NULL,NULL,NULL,NULL,NULL,NULL,64.79,'2025-11-14 00:30:39'),(11,11,103.00,4.12,NULL,NULL,103.00,NULL,NULL,NULL,NULL,NULL,NULL,NULL,103.00,'2025-11-14 00:30:39');
/*!40000 ALTER TABLE `nf_totais` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `nf_transporte`
--

DROP TABLE IF EXISTS `nf_transporte`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `nf_transporte` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nota_id` int NOT NULL,
  `transportadora_razao` varchar(255) DEFAULT NULL,
  `transportadora_cnpj_cpf` char(14) DEFAULT NULL,
  `frete_por_conta` tinyint DEFAULT NULL,
  `placa_veiculo` varchar(15) DEFAULT NULL,
  `uf_veiculo` char(2) DEFAULT NULL,
  `rntrc` varchar(50) DEFAULT NULL,
  `quantidade_volumes` int DEFAULT NULL,
  `especie` varchar(100) DEFAULT NULL,
  `marca` varchar(100) DEFAULT NULL,
  `numeracao` varchar(100) DEFAULT NULL,
  `peso_bruto` decimal(18,3) DEFAULT NULL,
  `peso_liquido` decimal(18,3) DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  KEY `nota_id` (`nota_id`),
  CONSTRAINT `nf_transporte_ibfk_1` FOREIGN KEY (`nota_id`) REFERENCES `nota_fiscal` (`id`) ON DELETE CASCADE,
  CONSTRAINT `nf_transporte_chk_1` CHECK ((`frete_por_conta` in (0,1,2)))
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `nf_transporte`
--

LOCK TABLES `nf_transporte` WRITE;
/*!40000 ALTER TABLE `nf_transporte` DISABLE KEYS */;
INSERT INTO `nf_transporte` VALUES (1,1,'EBAZAR.COM.BR LTDA','03007331012239',2,NULL,NULL,NULL,1,NULL,NULL,NULL,0.970,0.970,'2025-11-14 00:20:27'),(2,2,'EBAZAR.COM.BR LTDA','03007331012239',2,NULL,NULL,NULL,1,NULL,NULL,NULL,8.700,8.500,'2025-11-14 00:20:27'),(3,3,'MERCADO LIVRE',NULL,0,NULL,NULL,NULL,1,'PACOTE',NULL,'1',5.300,5.300,'2025-11-14 00:20:27'),(4,4,NULL,NULL,2,NULL,NULL,NULL,1,NULL,NULL,NULL,NULL,NULL,'2025-11-14 00:24:26'),(5,5,'EBAZAR.COM.BR LTDA','03007331012239',2,NULL,NULL,NULL,1,NULL,NULL,NULL,1.890,1.890,'2025-11-14 00:24:26'),(6,6,NULL,NULL,2,NULL,NULL,NULL,1,NULL,NULL,NULL,NULL,NULL,'2025-11-14 00:24:26'),(7,7,'EBAZAR.COM.BR LTDA','03007331012239',2,NULL,NULL,NULL,1,NULL,NULL,NULL,0.300,0.200,'2025-11-14 00:26:43'),(8,8,'EBAZAR.COM.BR LTDA','03007331012239',2,NULL,NULL,NULL,1,NULL,NULL,NULL,0.690,0.690,'2025-11-14 00:26:43'),(9,10,'EBAZAR.COM.BR LTDA','03007331012239',2,NULL,NULL,NULL,1,NULL,NULL,NULL,0.020,0.020,'2025-11-14 00:30:39'),(10,11,'EBAZAR.COM.BR LTDA','03007331012239',2,NULL,NULL,NULL,1,NULL,NULL,NULL,1.040,1.040,'2025-11-14 00:30:39');
/*!40000 ALTER TABLE `nf_transporte` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `nota_fiscal`
--

DROP TABLE IF EXISTS `nota_fiscal`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `nota_fiscal` (
  `id` int NOT NULL AUTO_INCREMENT,
  `numero` varchar(20) NOT NULL,
  `serie` varchar(20) DEFAULT NULL,
  `modelo` varchar(5) DEFAULT '55',
  `tipo_operacao` char(1) DEFAULT NULL,
  `natureza_operacao` varchar(200) DEFAULT NULL,
  `chave_acesso` char(44) DEFAULT NULL,
  `protocolo_autorizacao` varchar(80) DEFAULT NULL,
  `data_emissao` date DEFAULT NULL,
  `hora_emissao` time DEFAULT NULL,
  `data_saida_entrada` date DEFAULT NULL,
  `hora_saida_entrada` time DEFAULT NULL,
  `indicador_presenca` smallint DEFAULT NULL,
  `finalidade_emissao` smallint DEFAULT NULL,
  `observacoes_fisco` text,
  `emitente_id` int DEFAULT NULL,
  `destinatario_id` int DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  `updated_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  UNIQUE KEY `chave_acesso` (`chave_acesso`),
  KEY `emitente_id` (`emitente_id`),
  KEY `destinatario_id` (`destinatario_id`),
  KEY `chave_acesso_2` (`chave_acesso`),
  KEY `numero` (`numero`,`serie`),
  CONSTRAINT `nota_fiscal_ibfk_1` FOREIGN KEY (`emitente_id`) REFERENCES `emitente` (`id`) ON DELETE SET NULL,
  CONSTRAINT `nota_fiscal_ibfk_2` FOREIGN KEY (`destinatario_id`) REFERENCES `destinatario` (`id`) ON DELETE SET NULL,
  CONSTRAINT `nota_fiscal_chk_1` CHECK ((`tipo_operacao` in (_utf8mb4'0',_utf8mb4'1')))
) ENGINE=InnoDB AUTO_INCREMENT=12 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `nota_fiscal`
--

LOCK TABLES `nota_fiscal` WRITE;
/*!40000 ALTER TABLE `nota_fiscal` DISABLE KEYS */;
INSERT INTO `nota_fiscal` VALUES (1,'152129','002','55','1','Venda de mercadorias','41251014908713000162550020001521291377182039','141250331543 02/10/2025 22:59:07','2025-10-02','22:59:05','2025-10-02','22:59:05',NULL,NULL,NULL,1,1,'2025-11-14 00:20:27','2025-11-14 00:20:27'),(2,'702753','003','55','1','Venda de mercadorias','35251020777802000110550030007027531971750531','135253081854 15/10/2025 07:26:33','2025-10-15','07:26:30','2025-10-15','07:26:30',NULL,NULL,NULL,2,2,'2025-11-14 00:20:27','2025-11-14 00:20:27'),(3,'880902','003','55','1','VENDA DE MERCADORIA NC F/E LUCRO','35250825273443000187550030008809021010415877','135252169644 03/08/2025 10:50:42','2025-08-03','10:50:13','2025-08-03','10:50:13',NULL,NULL,NULL,3,3,'2025-11-14 00:20:27','2025-11-14 00:20:27'),(4,'1409','007','55','1','Venda de mercadorias','35250758910140000187550070000014091349908941','135252035525 22/07/2025 06:28:19','2025-07-22','06:26:19','2025-07-22','06:26:19',NULL,NULL,NULL,4,4,'2025-11-14 00:24:26','2025-11-14 00:24:26'),(5,'329894','002','55','1','Venda de mercadorias','35250837762181000101550020003298941208262883','135252230795 07/08/2025 20:00:13','2025-08-07','20:00:11','2025-08-07','20:00:11',NULL,NULL,NULL,5,1,'2025-11-14 00:24:26','2025-11-14 00:24:26'),(6,'4265','001','55','1','Venda de mercadorias','35250658909952000102550010000042651780039368','135251628001 16/06/2025 08:05:19','2025-06-16','08:03:18','2025-06-16','08:03:18',NULL,NULL,NULL,6,2,'2025-11-14 00:24:26','2025-11-14 00:24:26'),(7,'258211','002','55','1','Venda de mercadorias','35250646931819000173550020002582111606028569','135251579454 11/06/2025 09:37:19','2025-06-11','09:37:17','2025-06-11','09:37:17',NULL,NULL,NULL,7,2,'2025-11-14 00:26:43','2025-11-14 00:26:43'),(8,'263964','002','55','1','Venda de mercadorias','42250420717387000109550020002639641362406540','242250155698 27/04/2025 11:56:07','2025-04-27','11:56:06','2025-04-27','11:56:06',NULL,NULL,NULL,8,2,'2025-11-14 00:26:43','2025-11-14 00:26:43'),(9,'367249','005','55','1','VENDA PARA USO OU CONSUMO OU IMOBILIZADO','31250492660406005269550050003672491100342371','131250130089 25/04/2025 15:47:33','2025-04-25','15:47:33','2025-04-25','15:47:33',NULL,NULL,NULL,9,5,'2025-11-14 00:30:39','2025-11-14 00:30:39'),(10,'19351','002','55','1','Venda de mercadorias','35250455249174000184550020000193511096444680','135250964433 19/04/2025 21:09:47','2025-04-19','21:09:47',NULL,NULL,NULL,NULL,NULL,10,5,'2025-11-14 00:30:39','2025-11-14 00:30:39'),(11,'315165','001','55','1','Venda de mercadorias','35250437865863000131550010003151651107315660','135251073144 23/04/2025 22:51:48','2025-04-23','22:51:48','2025-04-23','22:51:48',NULL,NULL,NULL,11,5,'2025-11-14 00:30:39','2025-11-14 00:30:39');
/*!40000 ALTER TABLE `nota_fiscal` ENABLE KEYS */;
UNLOCK TABLES;
/*!40103 SET TIME_ZONE=@OLD_TIME_ZONE */;

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */;

-- Dump completed on 2025-11-13 21:34:46
