---
title: Skype for Business Server 2015 での監視データへのアクセス
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: '概要: は、ビジネス サーバー 2015 の Skype で使用される監視のデータについて説明します。'
ms.openlocfilehash: 908ebbff4e88985cdba606098dc5a5ace271e30d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="access-monitoring-data-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での監視データへのアクセス
 
**の概要:**ビジネス サーバー 2015 の Skype で使用される監視のデータについて説明します。
  
監視データは、2 つの SQL Server データベースに格納されます。LcsCdr には通話詳細記録データが格納され、QoEMetrics には QoE (Quality of Experience) データが格納されます。これら 2 つのデータベースについて特別なことは何もありません。つまり、これらのデータベースに格納されているデータには、SQL Server データのアクセスと分析に使用する一般的なツールでアクセスできます。
  
アクセスおよび監視データを分析する必要があります 1 つのツールは、サーバーの監視レポートのビジネス Skype です。 監視のレポートは、Microsoft SQL Server レポート サービスによって公開される標準レポートのセットです。 アクセスできる web ブラウザーを使用して、これらのレポートは、使用法、通話診断情報、およびメディアの品質については、すべてに基づく通話の詳細記録 (CDR) と高品質のエクスペリエンス (QoE) レコードが、CDR および QoE データベースに格納されているを提供します。 監視レポート ビジネス サーバー 2015 の Skype に付属し、インストールできます、Skype からビジネス サーバーの展開ウィザードの後、Skype のビジネス サーバーがインストールされており、監視が構成されています。
  
説明したように、監視レポートには SQL Server Reporting Service を使用する必要があります。SQL Server Reporting Service は、SQL Server のインストールと同時に、または SQL Server 自体をインストールした後でいつでも、インストールできます。
  
詳細については、「ビジネス サーバー 2015 展開ガイド 』 Skype の[ビジネス サーバー 2015 の Skype での監視レポートのインストール](../../deploy/deploy-monitoring/install-monitoring-reports.md)」を参照してください。
  

