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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: このトピックでは、オンプレミス PSTN 接続を使用してユーザー電話システムを有効にする方法について説明します。 このトピックの手順を実行する前に、次の内容を読む必要があります。
ms.openlocfilehash: 1706c91bc9e277da75253ab2f8675d6dc9c4c06c6057668f69cfd7da058691e3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288875"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Skype for Business Server でオンプレミス PSTN 接続を使用して電話システムのユーザーを有効にする

このトピックでは、オンプレミス PSTN 接続を使用してユーザー電話システムを有効にする方法について説明します。 このトピックの手順を実行する前に、次の内容を読む必要があります。
  
- ハイブリッド接続をセットアップする方法については、「Skype for Business Server と Skype for Business Online のハイブリッド接続を計画する」および[「Skype for Business Server](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)と Skype for Business Online のハイブリッド接続を展開する」[を参照してください](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。
    
- 展開の計画について詳しくは、「オンプレミス PSTN 接続電話システムを計画する」をご[覧Skype for Business Server。](plan-phone-system-with-on-premises-pstn-connectivity.md)
    
- ライセンスとプランを含む電話システムの詳細については、「PSTN 通話プラン for Skype for Business」[を参照してください](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。
    
> [!Important]
> Skype for Businessオンラインは 2021 年 7 月 31 日に廃止され、その後サービスにアクセスできなくなりました。  さらに、オンプレミス環境間の PSTN 接続は、Skype for Business Server または Cloud Connector Edition と Skype for Business Online の間でサポートされなくなりました。  直接ルーティングを使用してオンプレミスのテレフォニー ネットワークをネットワークにTeams[する方法について説明します](/MicrosoftTeams/direct-routing-landing-page)。

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>オンプレミス PSTN 接続電話システムユーザーをユーザーに移動する

ユーザーを Skype for Business Online に移動する前に、Skype for Business Server または Lync Server 2013 でオンプレミスのユーザーを有効にしてから、それらをオンラインに移動してください。 詳細については[、「Skype for Business Server](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)と Skype for Business Online のハイブリッド接続を計画する」および「オンプレミスの エンタープライズ VoIP のユーザーを有効にする[(ユーザー](enable-the-users-for-enterprise-voice-on-premises.md)がオンプレミスに接続されている間に実行される)」の特別な考慮事項セクションを参照してください。 
  
すべてのユーザーは、オンプレミスの Active Directory で作成され、サポートされているバージョンの Azure Microsoft 365 コネクタOffice 365を使用して、ADまたは同期する必要があります。 Azure 電話システムで電話システムされたOffice 365ユーザーを有効にAD。 Azure AD で作成されたユーザーに対してオンプレミス PSTN 接続を使用して 電話システム を有効にする場合は、オンプレミス AD でそのユーザーの新しいアカウントを作成し、オンプレミスでアカウントを構成し、サポートされているバージョンの Azure AD Connector ツールを使用してアカウントを同期する必要があります。 
  
オンプレミス PSTN 接続を使用電話システムユーザーを有効にしてから、オンラインに移動するには、次Skype for Business手順が必要です。
  
- [ユーザーがオンプレミスにエンタープライズ VoIPを有効にする](enable-the-users-for-enterprise-voice-on-premises.md)(ユーザーがオンプレミスに帰宅している間に実行されます)。
    
- [音声ルーティング ポリシーを割り当てる](assign-a-voice-routing-policy.md) (ユーザーがオンプレミスに接続されている間に実行されます)。
    
- [ユーザーをクラウドに同期し、ライセンスを割り当てる](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)(ユーザーを使用してOffice 365)。
    
- [オンプレミス ユーザーを [オンライン] Skype for Business](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md)に移動します (オンプレミスWindows PowerShellを使用して実行されますが、管理者の資格情報Office 365使用します)。
    
- [ユーザーがオンラインボイスエンタープライズ VoIPボイス電話システムを有効にする](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)(リモート PowerShell を使用して実行)。
