---
title: 組織での発信者番号の利用方法
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.voice.callerid.overview
ms.custom:
- Calling Plans
description: 発信者番号通知は、CallingLineIdentity と呼ばれるポリシーを使用して、電話システム ユーザーの着信と発信の両方で制御できます。
ms.openlocfilehash: 31948a8361d8ae5a15ce84549d982d0c7f9adf1b
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "36484039"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>組織での発信者番号の利用方法

発信者番号通知は、CallingLineIdentity と呼ばれるポリシーを使用して、電話システム ユーザーの着信と発信の両方で制御できます。
  
発信者番号通知機能は、PSTN 接続に関係なくすべての電話システムのユーザーが使用できます。
  
- オンラインの PSTN 接続
    
- Skype for Business Cloud Connector Edition を使用したオンプレミスの PSTN 接続 (Cloud Connector Edition 1.4.2 以降が必要です)
    
- Skype for Business Server を使用したオンプレミスの SPTN 接続 (Skype for Business Server 2015 CU5 以降が必要です）
    
> [!NOTE]
> このポリシーは、Skype for Business 2015 Server では使用できません。 
  
## <a name="outbound-caller-id"></a>発信側の発信者番号通知

発信側の PSTN 発信者番号通知に使用できるオプションは次の 3 つです。
  
- ユーザーに割り当てられた電話番号。既定です。
    
- Office 365 の電話番号インベントリの通話プランで*サービス*電話番号と*無料*電話番号として分類されている電話番号。 これは通常、組織の自動応答またはコール キューに割り当てられます。
    
- 非通知に設定。
    
ただし、以下の種類の電話番号を発信側の発信者番号通知に割り当てることはできません。
  
- 通話プランの電話番号インベントリで*ユーザー*として分類されているすべての電話番号。
    
- Skype for Business Server のオンプレミスの電話番号
    
発信側の発信者番号通知を設定するには、「[ユーザーの発信者番号通知を設定する](/microsoftteams/set-the-caller-id-for-a-user)」を参照してください。
  
### <a name="end-user-control-of-outbound-caller-id"></a>発信側の発信者番号通知のエンド ユーザー コントロール

EnableUserOverride 属性を使用すると、単独または複数のユーザーが発信者番号通知の設定を **非通知**に変更できます。 これが適用されるのは、CallingLineIdentity のポリシーが LineURI または Substitute のいずれかの CallingIDSubstitute パラメーターで構成されている場合のみです。 EnableUserOverride の既定値は False です。
  
エンドユーザーは、Skype for Business デスクトップクライアントの [**設定**] タブを使用して、自分の発信者番号を**匿名**に設定できます。 [**エンドユーザー**に電話をかける] (管理者によって有効になっている場合)、[**すべての通話に対して電話番号とプロフィール情報を非表示にする] を選択します。**.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**バージョン** <br/> |**サポートされ** <br/> |
|クイック実行  <br/> |2016 年 12 月 6 日 - バージョン 1611 (ビルド 7571.2072) でリリースされた現在のチャネル  <br/> |はい  <br/> |
|クイック実行  <br/> |2017 年 2 月 22日 - バージョン 1701 (ビルド 7766.2060) でリリースされた段階的提供チャネルの最初のリリース  <br/> |はい  <br/> |
|クイック実行  <br/> |2017年 6 月 13日 - バージョン 1701 (ビルド 7766.2092) でリリースされた段階的提供チャネル  <br/> |はい  <br/> |
|MSI  <br/> |Skype for Business  <br/> |いいえ  <br/> |
|Mac  <br/> |Skype for Business  <br/> |いいえ  <br/> |
   
## <a name="inbound-caller-id"></a>着信側の発信者番号通知

BlockIncomingCallerID 属性を使用すると、着信した PSTN 通話の発信者番号通知をブロックできます。 この属性を設定することはできますが、ユーザー設定ページではエンド ユーザーには使用できません。 また、現在はオンラインの PSTN 接続のみで使用可能です。
  
発信側の発信者番号通知を設定するには、「[ユーザーの発信者番号通知を設定する](/microsoftteams/set-the-caller-id-for-a-user)」を参照してください。
  
## <a name="related-topics"></a>関連トピック
[電話番号の移行に関するよくある質問](/microsoftteams/transferring-phone-numbers-common-questions)

[通話プランで使用されるさまざまな種類の電話番号](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
