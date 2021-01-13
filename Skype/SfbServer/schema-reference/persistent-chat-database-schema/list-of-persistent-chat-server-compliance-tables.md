---
title: Skype for Business Server の常設チャット サーバー コンプライアンス テーブルの一覧
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 常設チャット コンプライアンス データベース スキーマは、次の表で構成されます。
ms.openlocfilehash: 8fa9c47c2abd28922716cd42c5ff150ddd975393
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813057"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Skype for Business Server の常設チャット サーバー コンプライアンス テーブルの一覧
 
常設チャット コンプライアンス データベース スキーマは、次の表で構成されます。
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>常設チャット サーバーのコンプライアンス テーブルのリスト

|**Table**|**説明**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |構成済みのアダプターによってまだ処理されていないコンプライアンス イベントが格納されます。  <br/> この表には、チャット メッセージやファイルのダウンロードなど、常設チャット関連のイベントが含まれています。 (参加者イベントは tblComplianceParticipant テーブルによって追跡されます)。  <br/> (このテーブルのイベントを処理したサーバーは、tblComplianceFanout テーブルに含まれます)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |コンプライアンス イベントを処理したサーバーが格納されます。 このテーブルは tblComplianceData テーブルと緊密に結び付けられています。  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |チャット サービス別およびサーバー別に現在の参加者が格納されます。 常設チャット サービスから受信した参加イベントとパート コンプライアンス イベントに基づいて管理されます。  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |プール全体のコンプライアンス状態情報が含まれます。  <br/> |
   

