---
title: Skype for Business Server でオンプレミス PSTN 接続を使用して電話システムのユーザーを有効にする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: このトピックでは、オンプレミス PSTN 接続を使用してユーザー電話システムを有効にする方法について説明します。 このトピックの手順を実行する前に、次の内容を読む必要があります。
ms.openlocfilehash: ffd7e9f02466dddeef31ba7ffd3a194a04b9b2ff
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563664"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Skype for Business Server でオンプレミス PSTN 接続を使用して電話システムのユーザーを有効にする

このトピックでは、オンプレミス PSTN 接続を使用してユーザー電話システムを有効にする方法について説明します。 このトピックの手順を実行する前に、次の内容を読む必要があります。
  
- ハイブリッド接続をセットアップする方法については、「Skype for Business Server と Skype for Business[の](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)間のハイブリッド接続を計画する」および「ハイブリッド接続を展開する」を参照[Skype for Business Server。Skype for Business オンライン](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)です。
    
- 展開の計画について詳しくは、「オンプレミス PSTN 接続電話システムを計画する」をご[覧Skype for Business Server。](plan-phone-system-with-on-premises-pstn-connectivity.md)
    
- ライセンスとプランを含む電話システムの詳細については、「PSTN 通話プラン for Skype for Business」[を参照してください](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。
    
> [!Important]
> Skype for Business 2021 年 7 月 31 日にオンラインが廃止され、Skype for Business Server または Cloud Connector Edition と Skype for Business Online を通じたオンプレミス環境間の PSTN 接続はサポートされなくなりました。 直接ルーティングを使用してオンプレミスのテレフォニー ネットワークをネットワークにTeams[する方法について説明します](/MicrosoftTeams/direct-routing-landing-page)。

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>オンプレミス PSTN 接続電話システムユーザーをユーザーに移動する

ユーザーを Skype for Business Online に移動する前に、Skype for Business Server または Lync Server 2013 でオンプレミスのユーザーを有効にしてから、それらをオンラインに移動してください。 詳細については[、「Skype for Business Server](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)と Skype for Business Online のハイブリッド接続を計画する」および「オンプレミスの エンタープライズ VoIP のユーザーを有効にする[(ユーザー](enable-the-users-for-enterprise-voice-on-premises.md)がオンプレミスに接続されている間に実行される)」の特別な考慮事項セクションを参照してください。 
  
すべてのユーザーは、オンプレミスの Active Directory で作成され、サポートされているバージョンの Microsoft 365 コネクタOffice 365を使用して同期Azure AD必要があります。 ユーザーは、電話システムでOffice 365作成されたユーザーに対して有効Azure AD。 Azure AD で作成されたユーザーに対してオンプレミス PSTN 接続を使用して 電話システム を有効にする場合は、そのユーザーの新しいアカウントをオンプレミス AD で作成し、オンプレミスでアカウントを構成し、サポートされているバージョンの Azure AD Connector ツールを使用してアカウントを同期する必要があります。 
  
オンプレミス PSTN 接続を使用電話システムユーザーを有効にしてから、オンラインに移動するには、次Skype for Business手順が必要です。
  
- [ユーザーがオンプレミスにエンタープライズ VoIPを有効にする](enable-the-users-for-enterprise-voice-on-premises.md)(ユーザーがオンプレミスに帰宅している間に実行されます)。
    
- [音声ルーティング ポリシーを割り当てる](assign-a-voice-routing-policy.md) (ユーザーがオンプレミスに接続されている間に実行されます)。
    
- [ユーザーをクラウドに同期し、ライセンスを割り当てる](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)(ユーザーを使用してOffice 365)。
    
- [オンプレミス ユーザーを [オンライン] Skype for Business](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md)に移動します (オンプレミスWindows PowerShellを使用して実行されますが、管理者の資格情報Office 365使用します)。
    
- [ユーザーがオンラインボイスエンタープライズ VoIPボイス電話システムを有効にする](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)(リモート PowerShell を使用して実行)。
