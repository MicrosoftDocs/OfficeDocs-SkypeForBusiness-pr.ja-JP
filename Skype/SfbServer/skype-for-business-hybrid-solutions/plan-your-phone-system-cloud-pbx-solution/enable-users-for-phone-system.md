---
title: Skype for Business Server のオンプレミスの PSTN 接続を使用して、Office 365 で電話システムのユーザーを有効にする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: このトピックでは、Office 365 の電話システムで、オンプレミスの PSTN 接続を使用してユーザーを有効にする方法について説明します。 このトピックの手順を実行する前に、次の内容を参照してください。
ms.openlocfilehash: c8870cce90963e3a8d4e42de008df3eee779e52a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287462"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Skype for Business Server のオンプレミスの PSTN 接続を使用して、Office 365 で電話システムのユーザーを有効にする
 
このトピックでは、Office 365 の電話システムで、オンプレミスの PSTN 接続を使用してユーザーを有効にする方法について説明します。 このトピックの手順を実行する前に、次の内容を参照してください。
  
- ハイブリッド接続のセットアップ方法については、「 [skype For Business server と skype for Business online の間のハイブリッド接続の計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)」と「Skype For [Business server と Skype for business online の間にハイブリッド接続を導入](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)する」を参照してください。
    
- 展開の計画については、「 [Skype For Business Server でオンプレミスの PSTN 接続を使用して Office 365 で電話システムを計画](plan-phone-system-with-on-premises-pstn-connectivity.md)する」を参照してください。
    
- ライセンスやプランなど、Office 365 の電話システムの詳細については、「 [Skype For business の PSTN 通話プラン](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)」を参照してください。
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>オンプレミスの PSTN 接続を使用して、Office 365 の電話システムにユーザーを移動する

ユーザーを Skype for business Online に移行する前に、Skype for Business Server または Lync Server 2013 でオンプレミスのユーザーを有効にして、それらをオンラインで移行することをお勧めします。 詳細については、「 [skype For Business Server と skype For Business Online との間のハイブリッド接続の計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)」および「[エンタープライズ voip のユーザーを有効にする](enable-the-users-for-enterprise-voice-on-premises.md)(ユーザーのホームとして実行される)」の「特別な考慮事項」セクションを参照してください。オンプレミス)。 
  
すべてのユーザーは、オンプレミスの Active Directory で作成し、サポートされているバージョンの Azure AD コネクタを使用して Office 365 に同期する必要があります。 Azure AD で直接作成された Office 365 の電話システムのユーザーを有効にすることはできません。 Azure AD で作成されたユーザーのオンプレミスの PSTN 接続を使用して、Office 365 で電話システムを有効にするには、オンプレミスの AD でそのユーザーの新しいアカウントを作成し、そのアカウントをオンプレミスで構成して、次を使用してアカウントを同期する必要があります。サポートされている Azure AD コネクタツールのバージョン。 
  
Office 365 の電話システムでオンプレミスの PSTN 接続を有効にして、そのユーザーを Skype for Business Online に移行するには、次の手順を実行する必要があります。
  
- [オンプレミスのエンタープライズボイスのユーザーを有効にする](enable-the-users-for-enterprise-voice-on-premises.md)(ユーザーがオンプレミスでログオンしているときに実行されます)。
    
- [Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (ユーザーがオンプレミスに所属している間に実行します)。
    
- [ユーザーをクラウドと同期し、ライセンスを割り当てる](synchronize-users-to-the-cloud-and-assign-licenses.md)(Office 365 を使用して実行された場合)。
    
- [オンプレミスユーザーを Skype For Business Online に移動する](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online)(オンプレミスの Windows PowerShell を使用して実行しましたが、Office 365 管理者の資格情報を使用します)。
    
- [Office 365 でエンタープライズボイスオンラインおよび電話システムのユーザーを有効にする](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)(リモート PowerShell を使用して実行されました。
    

