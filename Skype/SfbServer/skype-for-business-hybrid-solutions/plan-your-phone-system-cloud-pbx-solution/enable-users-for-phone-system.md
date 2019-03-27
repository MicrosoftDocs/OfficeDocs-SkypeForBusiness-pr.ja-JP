---
title: ユーザー Office 365 の電話システムに Skype で設置した PSTN 接続を持つサーバーで有効にビジネス
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
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
description: 'このトピックでは、Office 365 の電話システムの設置の PSTN への接続を持つユーザーを有効にする方法について説明します。 このトピックの手順を実行する前に、以下を参照する必要があります: です。'
ms.openlocfilehash: a3eec7adbd4897889cbc2ef8c7e985231c53bc99
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889218"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>ユーザー Office 365 の電話システムに Skype で設置した PSTN 接続を持つサーバーで有効にビジネス
 
このトピックでは、Office 365 の電話システムの設置の PSTN への接続を持つユーザーを有効にする方法について説明します。 このトピックの手順を実行する前に、以下を参照する必要があります: です。
  
- ハイブリッド接続を設定する方法については、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間のハイブリッド接続を計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)し、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間のハイブリッド接続の展開](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)を参照してください。
    
- 展開の計画については、 [Skype のビジネス サーバーの PSTN への接続をオンプレミスと Office 365 の電話システムの計画](plan-phone-system-with-on-premises-pstn-connectivity.md)を参照してください。
    
- ライセンスおよび計画を含む、Office 365 の電話システムの詳細については、 [Skype をビジネスのための計画の PSTN の呼び出し](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)を参照してください。
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Office 365 の電話システムを設置した PSTN 接続を持つユーザーの移動

Skype をビジネス オンラインのユーザーを移動、する前に、ビジネスのサーバーまたは Lync Server 2013 では、Skype での社内ユーザーを有効にするを移動して、オンラインをお勧めします。 詳細についてを参照してください[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間でのハイブリッド接続を計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)し、特別な考慮事項のセクションを[設置型のエンタープライズ VoIP に対してユーザーを有効にする](enable-the-users-for-enterprise-voice-on-premises.md)(ユーザーが置かれているときに実行されます。設置)。 
  
すべてのユーザーは、オンプレミスの Active Directory で作成したし、Azure AD のコネクタのサポートされているバージョンを使用して Office 365 に同期する必要があります。 Azure AD で直接作成した Office 365 の電話システムのユーザーを有効にすることはできません。 設置型で、そのユーザー用に新しいアカウントを作成する必要があります Azure AD で作成されたユーザーに PSTN 接続を設置すると Office 365 の電話システムを有効にする場合は、AD は、アカウントの設置型を構成しを使用して、アカウントを同期Azure AD のコネクタ ツールのサポートされているバージョンです。 
  
Office 365 の電話システムの設置の PSTN への接続を持つユーザーを有効にして、オンライン ビジネスの Skype に移動して次の手順が必要です。
  
- [設置型のエンタープライズ VoIP に対してユーザーを有効にします。](enable-the-users-for-enterprise-voice-on-premises.md)(実行、ユーザーは、ホームの設置型)。
    
- [Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (ユーザーがオンプレミスに所属している間に実行します)。
    
- [同期ユーザーは、クラウドおよび割り当てのライセンス](synchronize-users-to-the-cloud-and-assign-licenses.md)(Office 365 を使用してを実行します。)
    
- [オンプレミス ユーザーがオンライン ビジネスの Skype を移動します。](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online)(Windows PowerShell の設置を使用していますが、Office 365 管理者の資格情報を使用して実行されます。)
    
- [ユーザーのエンタープライズ VoIP のオンラインと電話のシステムでは、Office 365 のボイスメールを有効にします。](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)(リモート PowerShell を使用して実行されます。
    

