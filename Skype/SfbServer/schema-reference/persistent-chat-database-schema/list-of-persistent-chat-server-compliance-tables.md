---
title: '[常設チャット サーバーのコンプライアンス テーブルの一覧] Skype for Business Server'
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
ms.openlocfilehash: b41d8a3f3c5e42f9e4c29eeb6cb81774b5b177aee18c67dc52bc4c9009f67c8e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303670"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>[常設チャット サーバーのコンプライアンス テーブルの一覧] Skype for Business Server
 
常設チャット コンプライアンス データベース スキーマは、次の表で構成されます。
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>常設チャット サーバーのコンプライアンス テーブルのリスト

|**表**|**Description**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |構成済みのアダプターによってまだ処理されていないコンプライアンス イベントが格納されます。  <br/> この表には、チャット メッセージやファイルのダウンロードなど、常設チャット関連のイベントが含まれています。 (参加者イベントは tblComplianceParticipant テーブルによって追跡されます)。  <br/> (このテーブルのイベントを処理したサーバーは、tblComplianceFanout テーブルに含まれます)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |コンプライアンス イベントを処理したサーバーが格納されます。このテーブルは tblComplianceData テーブルと緊密に結び付けられています。  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |チャット サービス別およびサーバー別に現在の参加者が格納されます。 これは、常設チャット サービスから受信した参加およびパーツのコンプライアンス イベントに基づいて維持されます。  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |プール全体のコンプライアンス状態情報が含まれます。  <br/> |
   

