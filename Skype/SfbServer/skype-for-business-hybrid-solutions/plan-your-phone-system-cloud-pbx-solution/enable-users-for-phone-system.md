---
title: Skype for Business Server でオンプレミスの PSTN 接続を使用して電話システムのユーザーを有効にする
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
description: このトピックでは、オンプレミスの PSTN 接続を備えた電話システムでユーザーを有効にする方法について説明します。 このトピックの手順を実行する前に、次の内容を確認する必要があります。
ms.openlocfilehash: 9cd5fe66b6092b0ac21af4c425f662d18d96ab49
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221097"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Skype for Business Server でオンプレミスの PSTN 接続を使用して電話システムのユーザーを有効にする
 
このトピックでは、オンプレミスの PSTN 接続を備えた電話システムでユーザーを有効にする方法について説明します。 このトピックの手順を実行する前に、次の内容を確認する必要があります。
  
- ハイブリッド接続をセットアップする方法については、「skype [for Business server と skype for Business online の間のハイブリッド接続を計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)する」および「Skype For [Business server と Skype for business online 間のハイブリッド接続を展開](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)する」を参照してください。
    
- 展開の計画については、「 [Plan Phone System with ON-PREMISES PSTN connectivity In Skype For Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md)」を参照してください。
    
- ライセンスやプランを含む電話システムの詳細については、「 [Skype for business の PSTN 通話プラン](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)」を参照してください。
    
## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>オンプレミスの PSTN 接続を備えた電話システムへのユーザーの移動

ユーザーを Skype for Business Online に移行する前に、Skype for business Server または Lync Server 2013 でユーザーをオンプレミスで有効にしてから、それらをオンラインに移行することをお勧めします。 詳細については、「 [Enable The Enterprise Voice on on-premises](enable-the-users-for-enterprise-voice-on-premises.md) (ユーザーがオンプレミスに所属している間に実行されます)」の「 [Skype for Business Server と Skype for business Online の間のハイブリッド接続を計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)する」および「特別な考慮事項」セクションを参照してください。 
  
サポートされているバージョンの Azure AD Connector を使用して、すべてのユーザーをオンプレミスの Active Directory に作成し、Microsoft 365 または Office 365 に同期する必要があります。 Office 365 の電話システムでは、Azure AD で直接作成されたユーザーを有効にすることはできません。 Azure AD で作成したユーザーに対してオンプレミスの PSTN 接続を備えた電話システムを有効にする場合は、オンプレミスの AD でそのユーザーの新しいアカウントを作成し、オンプレミスのアカウントを構成して、サポートされているバージョンの Azure AD Connector ツールを使用してアカウントを同期する必要があります。 
  
オンプレミスの PSTN 接続を備えた電話システムに対してユーザーを有効にし、それを Skype for Business Online に移動するには、次の手順を実行する必要があります。
  
- [エンタープライズ voip オンプレミスのユーザーを有効](enable-the-users-for-enterprise-voice-on-premises.md)にします (ユーザーがオンプレミスに所属している間に実行されます)。
    
- [音声ルーティングポリシーを割り当て](assign-a-voice-routing-policy.md)ます (ユーザーがオンプレミスに所属している間に実行されます)。
    
- [ユーザーをクラウドに同期し、ライセンスを割り当て](synchronize-users-to-the-cloud-and-assign-licenses.md)ます (Office 365 を使用して実行します)。
    
- オンプレミスの[ユーザーを Skype For Business Online に移動](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online)します (社内で Windows PowerShell を使用して実行しますが、Office 365 管理者の資格情報を使用します)。
    
- [エンタープライズ voip](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (リモート PowerShell を使用して実行される) ユーザーを有効にします。
    

