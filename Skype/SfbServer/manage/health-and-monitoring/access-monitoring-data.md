---
title: ネットワーク内の監視データにSkype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: '概要: サーバーで使用される監視データについてSkype for Business Server。'
ms.openlocfilehash: 416eeb0f1ec724b2d07200ce87d35a466336f9c1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763676"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>ネットワーク内の監視データにSkype for Business Server
 
**概要:** ネットワークで使用される監視データについてSkype for Business Server。
  
監視データは、2 つの SQL Server データベースに格納されます。LcsCdr には通話詳細記録データが格納され、QoEMetrics には QoE (Quality of Experience) データが格納されます。これら 2 つのデータベースについて特別なことは何もありません。つまり、これらのデータベースに格納されているデータには、SQL Server データのアクセスと分析に使用する一般的なツールでアクセスできます。
  
監視データにアクセスして分析するために考慮する必要があるツールの 1 つは、監視レポートSkype for Business Serverです。 監視レポートは、レポート サービスによって発行される一連の標準Microsoft SQL Serverです。 これらのレポートは、Web ブラウザーを使用してアクセス可能で、使用、通話診断情報、およびメディア品質情報を提供します。これらはすべて、CDR および QoE データベースに格納されている通話詳細記録 (CDR) および QoE (QoE) レコードに基づいて行います。 監視レポートは、Skype for Business Serverと一緒に出荷され、Skype for Business Serverがインストールされ、監視が構成されたSkype for Business Server展開ウィザードからインストールできます。
  
説明したように、監視レポートには SQL Server Reporting Service を使用する必要があります。SQL Server Reporting Service は、SQL Server のインストールと同時に、または SQL Server 自体をインストールした後でいつでも、インストールできます。
  
詳細については、「監視レポートのインストール[」を参照Skype for Business Server。](../../deploy/deploy-monitoring/install-monitoring-reports.md)
  

