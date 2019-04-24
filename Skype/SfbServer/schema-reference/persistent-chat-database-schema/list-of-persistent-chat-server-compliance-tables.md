---
title: ビジネス サーバーの Skype での永続的なチャット サーバー コンプライアンス テーブルの一覧
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 永続的なチャット コンプライアンス データベース スキーマは、次の表で構成されます。
ms.openlocfilehash: 18c35cc71da43dcf25bb477e81a2471b483ee86d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212699"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>ビジネス サーバーの Skype での永続的なチャット サーバー コンプライアンス テーブルの一覧
 
永続的なチャット コンプライアンス データベース スキーマは、次の表で構成されます。
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>永続的なチャット サーバー コンプライアンス テーブルの一覧

|**テーブル**|**説明**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |構成されているアダプターによってまだ処理されていないコンプライアンス イベントが含まれています。  <br/> このテーブルには、チャット メッセージやファイルのダウンロードなどの永続的なチャットに関連するイベントが含まれています。 (イベントの参加者は、tblComplianceParticipant テーブルで追跡されます)。  <br/> (この表に示すイベントを処理するサーバーは、tblComplianceFanout の表に一覧表示されます)。  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |コンプライアンス イベントを処理するサーバーが含まれています。 次の表は、tblComplianceData テーブルと密接に関連します。  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |チャット サービスおよびサーバーごとの現在の参加者が含まれています。 永続的なチャット サービスから受信した結合し、一部のコンプライアンス イベントに基づいて保持されます。  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |プール全体にわたるコンプライアンスの状態情報が含まれています。  <br/> |
   

