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
description: このトピックでは、オンプレミスの PSTN 接続を使用して電話システムのユーザーを有効にする方法について説明します。 このトピックの手順を実行する前に、次の内容を読む必要があります。
ms.openlocfilehash: 0a843b49546bfc5451197a3ef8ca48799c194731
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120869"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Skype for Business Server でオンプレミス PSTN 接続を使用して電話システムのユーザーを有効にする

このトピックでは、オンプレミスの PSTN 接続を使用して電話システムのユーザーを有効にする方法について説明します。 このトピックの手順を実行する前に、次の内容を読む必要があります。
  
- ハイブリッド接続をセットアップする方法については [、「Skype for Business Server](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) と Skype for Business Online のハイブリッド接続を計画する」および [「Skype for](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)Business Server と Skype for Business Online のハイブリッド接続を展開する」を参照してください。
    
- 展開の計画の詳細については、「Skype for Business Server でオンプレミス PSTN 接続を使用して電話システムを計画 [する」を参照してください](plan-phone-system-with-on-premises-pstn-connectivity.md)。
    
- ライセンスとプランを含む電話システムの詳細については [、「SKYPE for Business の PSTN 通話プラン」を参照してください](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。
    
> [!Important]
> Skype for Business Online は 2021 年 7 月 31 日に廃止され、その後サービスにアクセスできなくなりました。  さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online を介したオンプレミス環境間の PSTN 接続はサポートされなくなりました。  直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>オンプレミス PSTN 接続を使用してユーザーを電話システムに移動する

ユーザーを Skype for Business Online に移行する前に、Skype for Business Server または Lync Server 2013 でオンプレミスのユーザーを有効にしてから、それらをオンラインに移動してください。 詳細については [、「Skype for Business Server](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) と Skype for Business Online 間のハイブリッド接続を計画する」および「オンプレミスの [エンタープライズ VoIP](enable-the-users-for-enterprise-voice-on-premises.md) のユーザーを有効にする (ユーザーがオンプレミスに接続されている間に実行される)」の特別な考慮事項セクションを参照してください。 
  
すべてのユーザーをオンプレミスの Active Directory で作成し、サポートされているバージョンの Azure AD Connector を使用して Microsoft 365 または Office 365 に同期する必要があります。 Azure 365 で直接作成された Office 365 で電話システムのユーザーを有効AD。 Azure AD で作成されたユーザーに対してオンプレミス PSTN 接続を使用して電話システムを有効にする場合は、オンプレミス AD でそのユーザーの新しいアカウントを作成し、オンプレミスでアカウントを構成し、サポートされているバージョンの Azure AD Connector ツールを使用してアカウントを同期する必要があります。 
  
オンプレミスの PSTN 接続を使用して電話システムのユーザーを有効にしてから、Skype for Business Online に移動するには、次の手順が必要です。
  
- [ユーザーがオンプレミスにエンタープライズ VoIPを有効にする](enable-the-users-for-enterprise-voice-on-premises.md) (ユーザーがオンプレミスに設定されている間に実行されます)。
    
- [音声ルーティング ポリシーを割り当てる](assign-a-voice-routing-policy.md) (ユーザーがオンプレミスに接続されている間に実行されます)。
    
- [ユーザーをクラウドに同期し、ライセンスを割り当てる](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) (Office 365 を使用して実行)。
    
- [オンプレミス のユーザーを Skype for Business Online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) に移動します (Windows PowerShellを使用して実行しますが、365 管理者の資格情報Office使用します)。
    
- [オンラインおよび電話システムボイスエンタープライズ VoIPユーザーを有効にする](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (リモート PowerShell を使用して実行)。
