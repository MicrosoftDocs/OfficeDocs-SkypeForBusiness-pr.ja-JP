---
title: 組織での発信者番号の利用方法
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: 発信者番号通知は、CallingLineIdentity と呼ばれるポリシーを使用して、電話システム ユーザーの着信と発信の両方で制御できます。
ms.openlocfilehash: e723311b2780dd1d43bad4874b72133e09ff4fc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120678"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>組織での発信者番号の利用方法

発信者番号通知は、CallingLineIdentity と呼ばれるポリシーを使用して、電話システム ユーザーの着信と発信の両方で制御できます。
  
発信者番号機能は、PSTN 接続電話システム、すべてのユーザーが使用できます。

- Microsoft 通話プラン 

- 電話システムのダイレクト ルーティング 
  
- オンラインの PSTN 接続
    
- Skype for Business Cloud Connector Edition を使用したオンプレミスの PSTN 接続 (Cloud Connector Edition 1.4.2 以降が必要です)
    
- Skype for Business Server を使用したオンプレミスの SPTN 接続 (Skype for Business Server 2015 CU5 以降が必要です）
    
> [!NOTE]
> このポリシーは、Skype for Business 2015 Server では使用できません。 
  
## <a name="outbound-caller-id"></a>発信側の発信者番号通知

発信 PSTN 発信者番号には、次の 3 つのオプションがあります。
  
- ユーザーに割り当てられた電話番号。既定です。
    
- 通話プランの電話番号インベントリでサービスとして分類される電話番号と無料電話番号。 これは通常、組織の自動応答またはコール キューに割り当てられます。
    
- 非通知に設定。
    
ただし、以下の種類の電話番号を発信側の発信者番号通知に割り当てることはできません。
  
- 通話プランの電話番号インベントリで *ユーザー* として分類されているすべての電話番号。
    
- Skype for Business Server のオンプレミスの電話番号
    
発信側の発信者番号通知を設定するには、「[ユーザーの発信者番号通知を設定する](./set-the-caller-id-for-a-user.md)」を参照してください。
  
### <a name="end-user-control-of-outbound-caller-id"></a>送信呼び出し元 ID のエンド ユーザー制御

EnableUserOverride 属性を使用すると、1 人または複数のユーザーが発信者番号の設定を Anonymous に **変更できます**。 これが適用されるのは、CallingLineIdentity のポリシーが LineURI または Substitute のいずれかの CallingIDSubstitute パラメーターで構成されている場合のみです。 EnableUserOverride の既定値は False です。
  
エンド ユーザーは、Skype for Business デスクトップクライアントの **設定** タブを使用して発信者番号を匿名に設定し、[エンド ユーザーの呼び出し] **(管理者** が有効になっている場合) を選択し、[すべての通話で電話番号とプロファイル情報を非表示にする] を選択 **します。** このTeams、ユーザーは右上隅にある自分のプロフィール画像に移動し **、[設定** 通話] を選択し、[発信者番号] で [すべての通話の電話番号とプロファイル情報を非表示にする] を選択します  >  。  
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**バージョン** <br/> |**サポートされています** <br/> |
|クイック実行  <br/> |2016 年 12 月 6 日 - バージョン 1611 (ビルド 7571.2072) でリリースされた現在のチャネル  <br/> |はい  <br/> |
|クイック実行  <br/> |2017 年 2 月 22日 - バージョン 1701 (ビルド 7766.2060) でリリースされた段階的提供チャネルの最初のリリース  <br/> |はい  <br/> |
|クイック実行  <br/> |2017年 6 月 13日 - バージョン 1701 (ビルド 7766.2092) でリリースされた段階的提供チャネル  <br/> |はい  <br/> |
|MSI  <br/> |Skype for Business  <br/> |いいえ  <br/> |
|Mac  <br/> |Skype for Business  <br/> |いいえ  <br/> |
   
## <a name="inbound-caller-id"></a>受信呼び出し元 ID

電話システムは、その番号が Azure AD のユーザーに関連付けられている場合、外部電話番号の呼び出し ID を表示します。 電話番号が Azure ADではない場合は、電話会社が指定した表示名が表示されます (使用可能な場合)。

BlockIncomingCallerID 属性を使用すると、着信した PSTN 通話の発信者番号通知をブロックできます。 この属性を設定することはできますが、ユーザー設定ページではエンド ユーザーには使用できません。 また、現在はオンラインの PSTN 接続のみで使用可能です。
  
発信側の発信者番号通知を設定するには、「[ユーザーの発信者番号通知を設定する](./set-the-caller-id-for-a-user.md)」を参照してください。
  
## <a name="related-topics"></a>関連トピック
[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
