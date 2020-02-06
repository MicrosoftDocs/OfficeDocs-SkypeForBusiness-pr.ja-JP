---
title: Skype for Business Server の常設チャットサーバーのコンプライアンステーブルの一覧
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 常設チャットのコンプライアンスデータベーススキーマは、次の表で構成されています。
ms.openlocfilehash: a992f00718d831af1b5a30f08baaf779ea3ee2c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814765"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Skype for Business Server の常設チャットサーバーのコンプライアンステーブルの一覧
 
常設チャットのコンプライアンスデータベーススキーマは、次の表で構成されています。
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>常設チャットサーバーのコンプライアンステーブルの一覧

|**テーブル**|**説明**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |構成済みのアダプターによってまだ処理されていないコンプライアンスイベントが含まれています。  <br/> この表には、チャットメッセージやファイルのダウンロードなどの常設チャット関連イベントが含まれています。 (参加者のイベントは、tblComplianceParticipant テーブルによって追跡されます)。  <br/> (この表のイベントを処理したサーバーは、tblComplianceFanout テーブルに一覧表示されます)。  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |コンプライアンスイベントを処理したサーバーが含まれます。 この表は、tblComplianceData テーブルと密接に結び付いています。  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |チャットサービスとサーバーごとに現在の参加者が含まれます。 これは、常設チャットサービスから受信した参加イベントとパートコンプライアンスイベントに基づいて維持されます。  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |プール全体のコンプライアンスの状態に関する情報が含まれています。  <br/> |
   

