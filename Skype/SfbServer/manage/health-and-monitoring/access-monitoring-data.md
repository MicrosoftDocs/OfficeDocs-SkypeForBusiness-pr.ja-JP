---
title: アクセス Skype 内のデータをビジネスのサーバーの監視
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: '概要: は、Skype のビジネスのサーバーが使用する監視データについて説明します。'
ms.openlocfilehash: 4bd7d7c55f2d041d1bd3d80cf056544cd5bf5ee1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986587"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>アクセス Skype 内のデータをビジネスのサーバーの監視
 
**の概要:** ビジネス サーバーの Skype で使用される監視のデータについて説明します。
  
監視データは、2 つの SQL Server データベースに格納されます。LcsCdr には通話詳細記録データが格納され、QoEMetrics には QoE (Quality of Experience) データが格納されます。これら 2 つのデータベースについて特別なことは何もありません。つまり、これらのデータベースに格納されているデータには、SQL Server データのアクセスと分析に使用する一般的なツールでアクセスできます。
  
アクセスおよび監視データを分析する必要があります 1 つのツールは、サーバーの監視レポートのビジネス Skype です。 監視のレポートは、Microsoft SQL Server レポート サービスによって公開される標準レポートのセットです。 アクセスできる web ブラウザーを使用して、これらのレポートは、使用法、通話診断情報、およびメディアの品質については、すべてに基づく通話の詳細記録 (CDR) と高品質のエクスペリエンス (QoE) レコードが、CDR および QoE データベースに格納されているを提供します。 監視レポートでは、ビジネス サーバーの Skype で発送しからインストールすること、Skype ビジネス サーバーの展開ウィザードの後、Skype のビジネス サーバーがインストールされており、監視が構成されています。
  
説明したように、監視レポートには SQL Server Reporting Service を使用する必要があります。SQL Server Reporting Service は、SQL Server のインストールと同時に、または SQL Server 自体をインストールした後でいつでも、インストールできます。
  
詳細については、「 [Skype ビジネス サーバーの [監視レポートのインストール](../../deploy/deploy-monitoring/install-monitoring-reports.md)」を参照してください。
  

