---
title: 組織での発信者番号の利用方法
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: 発信者番号通知は、CallingLineIdentity と呼ばれるポリシーを使用して、電話システム ユーザーの着信と発信の両方で制御できます。
ms.openlocfilehash: 250f8a1a516aec4c9941b0c6396e6d44771b4f53
ms.sourcegitcommit: f608811288c82a6348a6af1671246a93ed06e578
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66660963"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>組織での発信者番号の利用方法

発信者番号は、次の 2 つのユーザー向け情報で構成されます。

- 電話番号 (CLID または通話回線 ID と呼ばれます)。 これは、発信者の識別として表示される公衆交換電話網 (PSTN) 番号です。

- 発信側の名前 (通常は CNAM と呼ばれます)。 
  
発信者番号機能は、 [PSTN 接続オプション](pstn-connectivity.md) (Microsoft 通話プラン、オペレーター接続、またはダイレクト ルーティング) に関係なく、すべての Phone System ユーザーが利用できます。 
  
CallingLineIdentity というポリシーを使用して、着信呼び出しと発信呼び出しの両方の呼び出し元 ID を制御できます。 詳細については、「 [通話回線 ID と発信者名の詳細](more-about-calling-line-id-and-calling-party-name.md)」を参照してください。

  
## <a name="outbound-pstn-caller-id"></a>発信 PSTN 発信者番号

発信 PSTN 発信者番号については、次のオプションを使用できます。 
  
- ユーザーに割り当てられた電話番号。既定です。

- 匿名。ユーザーの PSTN 番号のプレゼンテーションを削除することで使用できます。 

- 次の代替電話番号を指定できます。

  - 通話プランの電話番号インベントリで、サービスとフリーダイヤル番号として分類される電話番号。 Teams 自動応答または通話キューに割り当てられます。

  - Teams 自動応答または通話キューによって使用されるリソース アカウントに割り当てられる、ダイレクト ルーティングを介したオンプレミスの電話番号。 

- 発信 PSTN 通話に設定された発信側の名前または CNAM。  
    
詳細については、「 [ユーザーの呼び出し元 ID を設定する」を参照してください](./set-the-caller-id-for-a-user.md)。
  
### <a name="end-user-control-of-outbound-caller-id"></a>送信呼び出し元 ID のエンド ユーザー制御

ユーザーは EnableUserOverride 属性を設定することで、発信者番号の設定を **匿名** に変更できます。 

送信呼び出し元 ID が匿名に設定されている場合、EnableUserOverride は無効になり、呼び出し元 ID は常に匿名に設定されます。 EnableUserOverride の既定値は False です。

エンド ユーザーは **、[設定] > [通話]** に移動して発信者番号を匿名に設定し、[ **発信者番号]** で **[すべての通話の電話番号とプロファイル情報を非表示にする**] を選択します。 この設定変更が新しい呼び出しに反映されるまで数分かかります。 

### <a name="notes"></a>メモ

以下の点について留意してください。

- 発信発信者番号に次の種類の電話番号を割り当てることはできません。

  - 通話プランの電話番号インベントリでユーザーとして分類されるすべての電話番号。

  - ユーザーに割り当てられている直接ルーティングを介したオンプレミスの電話番号。

  - オンプレミスの電話番号Skype for Business Server。

- リソース アカウント電話番号の置換の使用は、Teams ユーザーに対して機能します。 サービス電話番号の置き換えは、Teams ユーザーに対して機能します。

- 発信者名は、発信者 ID が LineUri、サービスまたはリソース アカウントの電話番号で置き換え、発信者が Teams ユーザーの場合に送信されます。

- 発信側のパーティー名には最大 200 文字を指定できますが、ダウンストリーム システムではサポートされる文字数が少なくなる場合があります。

- ダイレクト ルーティングでは、電話番号の置換と発信側の名前が FROM SIP ヘッダーに送信されます。 対応する OnlinePstnGateway が ForwardPai = True で構成されている場合、P-ASSERTED-IDENTITY SIP ヘッダーには実際の呼び出し元ユーザーが含まれます。

- EnableUserOverride は、ポリシー内の他の設定よりも優先されます。置換が匿名に設定されている場合を除きます。 たとえば、ポリシー インスタンスがリソース アカウントを使用して置換され、EnableUserOverride が設定され、ユーザーによって有効になっているとします。 この場合、送信呼び出し元 ID がブロックされ、匿名が使用されます。 ポリシー インスタンスの置換が匿名に設定され、EnableUserOverride が設定されている場合、送信呼び出し元 ID はエンド ユーザー設定に関係なく常に匿名になります。

   
## <a name="inbound-caller-id"></a>受信呼び出し元 ID

電話システムでは、着信外部電話番号が発信者番号として表示されます。 番号が Azure AD のユーザーまたは連絡先、または個人の連絡先に関連付けられている場合、Skype for Businessクライアントと Teams クライアントは、その情報に基づいて発信者番号を表示します。 電話番号が Azure AD または個人の連絡先にない場合は、電話番号が利用可能な場合は、電話会社が指定した表示名が表示されます。

BlockIncomingCallerID 属性を使用すると、着信した PSTN 通話の発信者番号通知をブロックできます。 この属性を設定することはできますが、ユーザー設定ページではエンド ユーザーには使用できません。 この設定を有効にすると、着信 PSTN 発信者は匿名からの着信として表示されます。
  
着信呼び出し元 ID をブロックするには、「 [ユーザーの呼び出し元 ID を設定する」を参照してください](./set-the-caller-id-for-a-user.md)。
  
## <a name="related-topics"></a>関連項目
[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
