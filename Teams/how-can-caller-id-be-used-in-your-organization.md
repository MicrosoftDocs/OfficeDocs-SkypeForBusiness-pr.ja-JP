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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: 発信者番号通知は、CallingLineIdentity と呼ばれるポリシーを使用して、電話システム ユーザーの着信と発信の両方で制御できます。
ms.openlocfilehash: 43d3d6633ca46485aa111a7d97b9bd37b0547818
ms.sourcegitcommit: 02e243d6c58eab463a00ed45dadd80112087006e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2021
ms.locfileid: "52723548"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>組織での発信者番号の利用方法

呼び出し元 ID は、次の 2 つのユーザー向け識別可能な情報で構成されます。

- 電話番号 (通常は CLID または通話回線 ID と呼ばれます)。 これは、発信者の識別として表示される公衆交換電話番号 (PSTN) です。

- 呼び出し元の名前 (通常は CNAM と呼ばれます)。 
  
発信者番号機能は、PSTN 接続オプション電話システム、すべてのユーザーが使用できます。

- Microsoft 通話プラン 

- 電話システムのダイレクト ルーティング 
  
CallingLineIdentity というポリシーを使用して、着信呼び出しと送信呼び出しの両方の呼び出し元 ID を制御できます。 詳細については、「通話回線 [ID」と「通話相手名」を参照してください](more-about-calling-line-id-and-calling-party-name.md)。

  
## <a name="outbound-pstn-caller-id"></a>発信 PSTN 発信者番号

発信 PSTN 発信者番号については、次のオプションを使用できます。 
  
- ユーザーに割り当てられた電話番号。既定です。

- 匿名。ユーザーの PSTN 番号のプレゼンテーションを削除することで使用できます。 

- 代わりの電話番号。次の場合があります。

  - 通話プランの電話番号インベントリでサービスとして分類される電話番号と無料電話番号。 通常は、通話キューまたは通話キュー Teams 自動応答割り当てられます。

  - 直接ルーティングを介したオンプレミスの電話番号。この電話番号は、Teams 自動応答 または通話キューによって使用されるリソース アカウントに割り当てられます。 

- 発信 PSTN 通話で設定された発信側名または CNAM。  
    
詳細については、「ユーザーの発信者 [番号を設定する」を参照してください](./set-the-caller-id-for-a-user.md)。
  
### <a name="end-user-control-of-outbound-caller-id"></a>送信呼び出し元 ID のエンド ユーザー制御

ユーザーは、EnableUserOverride 属性を **設定することで** 、発信者番号の設定を Anonymous に変更できます。 

発信呼び出し元 ID が Anonymous に設定されている場合、EnableUserOverride は効果を持たず、呼び出し元 ID は常に Anonymous に設定されます。 EnableUserOverride の既定値は False です。

エンド ユーザーは **、[設定 >** 通話] に進み、[発信者番号] で [すべての通話の電話番号とプロファイル情報を非表示にする] を選択して、発信者番号を匿名に **設定できます**。

### <a name="notes"></a>備考

以下の点について留意してください。

- 発信発信者番号には、次の種類の電話番号を割り当てできません。

  - 通話プランの電話番号インベントリでユーザーとして分類される電話番号。

  - ユーザーに割り当てられている直接ルーティングによるオンプレミスの電話番号。

  - オンプレミスSkype for Business Server電話番号を入力します。

- リソース アカウントの電話番号の置き換えの使用は、ユーザーがTeamsします。 サービス電話番号の置き換えは、オンラインとユーザー Skype for Business両方Teams機能します。

- 発信者名は、発信者 ID が LineUri、サービスまたはリソース アカウントの電話番号に置き換わり、発信者が Teams ユーザーである場合にのみ送信されます。

- 通話パーティー名の最大文字数は 200 文字ですが、ダウンストリーム システムではサポートされる文字が少ない場合があります。

- ダイレクト ルーティングの場合、電話番号の置き換えと通話相手名は FROM SIP ヘッダーで送信されます。 対応する OnlinePstnGateway が ForwardPai = True で構成されている場合、P-ASSERTED-IDENTITY SIP ヘッダーには実際の呼び出し元ユーザーが含まれます。

- EnableUserOverride は、置換が Anonymous に設定されていない限り、ポリシー内の他の設定よりも優先されます。 たとえば、ポリシー インスタンスがリソース アカウントを使用して置き換え、EnableUserOverride がユーザーによって設定および有効になっているとします。 この場合、発信呼び出し元 ID はブロックされ、Anonymous が使用されます。 ポリシー インスタンスで置換が Anonymous に設定され、EnableUserOverride が設定されている場合、送信呼び出し元 ID はエンド ユーザーの設定に関係なく常に Anonymous になります。

   
## <a name="inbound-caller-id"></a>受信呼び出し元 ID

電話システム、着信した外部電話番号が発信者番号として表示されます。 番号が Azure AD または個人の連絡先のユーザーまたは連絡先に関連付けられている場合、Skype for Business クライアントと Teams クライアントには、その情報に基づいて発信者番号が表示されます。 電話番号が Azure AD または個人の連絡先に含されていない場合は、電話会社が提供する表示名が表示されます (使用可能な場合)。

BlockIncomingCallerID 属性を使用すると、着信した PSTN 通話の発信者番号通知をブロックできます。 この属性を設定することはできますが、ユーザー設定ページではエンド ユーザーには使用できません。 この設定を有効にすると、着信 PSTN 発信者は匿名からの発信元として表示されます。
  
受信呼び出し元 ID をブロックするには、「 [ユーザーの発信者番号を設定する」を参照してください](./set-the-caller-id-for-a-user.md)。
  
## <a name="related-topics"></a>関連項目
[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
