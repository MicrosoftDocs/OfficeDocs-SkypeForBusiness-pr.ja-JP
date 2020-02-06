---
title: Skype for Business Server でのアクセスの監視データ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: '概要: Skype for Business Server で使用されている監視データについて説明します。'
ms.openlocfilehash: b4eca36a09c4aa56b7216b476e0f0c5fa06d7a45
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818188"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Skype for Business Server でのアクセスの監視データ
 
**概要:** Skype for Business Server で使用されている監視データについて説明します。
  
監視データは、2 つの SQL Server データベースに格納されます。LcsCdr には通話詳細記録データが格納され、QoEMetrics には QoE (Quality of Experience) データが格納されます。これら 2 つのデータベースについて特別なことは何もありません。つまり、これらのデータベースに格納されているデータには、SQL Server データのアクセスと分析に使用する一般的なツールでアクセスできます。
  
監視データへのアクセスと分析について考慮すべきツールの1つは、Skype for Business Server Monitoring レポートです。 レポートの監視は、Microsoft SQL Server Reporting Service によって公開された標準レポートのセットです。 これらのレポートは、web ブラウザーを使用してアクセスできます。これらのレポートは、CDR と QoE データベースに保存されている通話の詳細記録 (CDR) と Quality of Experience (QoE) レコードに基づいて提供されます。 Skype for business server に同梱されている監視レポートは、skype for Business Server のインストールと監視が構成された後に、Skype for business server Deployment ウィザードからインストールできます。
  
説明したように、監視レポートには SQL Server Reporting Service を使用する必要があります。SQL Server Reporting Service は、SQL Server のインストールと同時に、または SQL Server 自体をインストールした後でいつでも、インストールできます。
  
詳細については、「 [Skype For Business Server で監視レポートをインストール](../../deploy/deploy-monitoring/install-monitoring-reports.md)する」を参照してください。
  

