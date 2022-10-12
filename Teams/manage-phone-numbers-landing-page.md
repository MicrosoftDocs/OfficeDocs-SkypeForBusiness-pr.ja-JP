---
title: 組織のために電話番号を管理する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davlick, roykuntz, jenstr
ms.topic: conceptual
ms.assetid: 6b61cb3c-361c-48a8-a9ef-d81bddde27bb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.overview
- ms.teamsadmincenter.voice.searchandacquire.PSTNpartner
- ms.lync.lac.NewNumberManualAcquisitionOpenSupportTicket
- ms.lync.lac.VASAMissingGeoCodes
- Calling Plans
- seo-marvel-apr2020
description: 組織の Microsoft Teams のユーザー (サブスクライバー) とサービス (有料および無料) の電話番号を取得および管理する方法について説明します。
ms.openlocfilehash: 053d886a97591a6685582f0db0ca194eaa312896
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551891"
---
# <a name="manage-telephone-numbers-for-your-organization"></a>組織の電話番号を管理する

現在、Microsoft では次の 2 つの電話番号の種類がサポートされています。 

- [**ユーザー番号**](#user-telephone-numbers)はサブスクライバー番号とも呼ばれ、組織内のユーザーに割り当てることができます。

- [**サービス番号**](#service-telephone-numbers)。 [電話会議](deploy-audio-conferencing-teams-landing-page.md)、 [自動応答](plan-auto-attendant-call-queue.md)、 [通話キュー](plan-auto-attendant-call-queue.md)などのサービスに割り当てられます。

Microsoft は数値型の簡略化に取り組んでいますが、現時点では次のことを決定する必要があります。

- Microsoft から新しい電話番号が必要なユーザーの場所はどれですか?
- どの種類の電話番号が必要ですか (サブスクライバーまたはサービス)?
- 既存の電話番号を Teams に移植操作方法?

電話番号を取得および管理する方法は、公衆交換電話網 (PSTN) 接続オプションによって異なります。

- Microsoft 通話プランの電話番号の管理については、「通話プラン [の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。

- オペレーター接続の電話番号の管理については、「オペレーター接続 [を使用して電話番号を設定する](operator-connect-configure.md#set-up-phone-numbers)」を参照してください。

- Teams Phone Mobile の電話番号の管理については、「Teams Phone Mobile [で電話番号を設定](operator-connect-mobile-configure.md#set-up-phone-numbers)する」を参照してください。

- ダイレクト ルーティングの電話番号の管理の詳細については、「電話番号 [を構成し、エンタープライズ音声を有効にする](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice)」を参照してください。




> [!NOTE]
> Microsoft Teams 管理センターに表示されている番号以外の追加または他の番号の種類が必要な場合は、電話番号 [サービス センター](https://pstnsd.powerappsportals.com/)に電話番号の要求を送信できます。

## <a name="user-telephone-numbers"></a>ユーザーの電話番号

組織内のユーザーに割り当てることができるユーザー電話番号には、次の 2 種類があります。  
    
- **地理的な数値** は地理的な領域との関係を持ち、最も一般的です。 たとえば、ほとんどの場合、地理的な電話番号は、国の特定の住所、都市、州、または地域内でのみ使用できます。
    
- **地理的でない数値** は、国番号または場合によっては VoIP 番号と呼ばれます。 これらの数値には、国/地域内の地理的領域との関係はありません。 たとえば、国/地域内の任意の場所から番号を呼び出すときに、非地理的な数値に同じコストがかかることがよくあります。 また、デンマークなどの一部の国では、地理的でない番号しか使用できません。


## <a name="service-telephone-numbers"></a>サービスの電話番号  

このセクションでは、ライセンスに含まれる Microsoft から入手できるサービス番号について説明します。 Operator Connect または Direct Routing によって提供されるサービス番号については、プロバイダーにお問い合わせください。 

Microsoft-Toll とフリーダイヤルによって提供されるサービス電話番号には、電話会議、自動応答、通話キューなどのサービスに割り当てることができる 2 種類のサービス電話番号があります。 サービス番号は、ユーザー番号よりも高い同時呼び出し容量を持っています。 サービス番号の可用性は、国/地域、番号の種類 (有料またはフリーダイヤルのどちらでも) によって異なります。 Microsoft の国/地域ごとのテレフォニー ライセンスによって、使用できる番号が決まります。
    
 - **有料サービス番号 - 有料サービス番号** には次の 2 種類があり、発信者に有料料金が発生する可能性があります。
    
   - **地域番号** 地理的な数値には、地理的領域とのリレーションシップがあります。 たとえば、ほとんどの場合、地理的な電話番号は、国の特定の住所、都市、州、または地域内でのみ使用できます。
        
   - **地理的でない数値** 非地理的数値は、国/地域内の地理的領域との関係を持たない国番号です。 たとえば、国/地域内の任意の場所から番号を呼び出すときに、非地理的な数値に同じコストがかかることがよくあります。
   
- **無料サービス番号** - これらのサービス番号は、通常、呼び出し元に有料料金は発生しません。 Teams は、60 を超える国/地域で国内のフリーダイヤル番号を提供しています。
    
    > [!CAUTION]
    > 一部の国/地域や発信番号の種類 (携帯電話から発信された通話など) では、発信者に有料料金が発生する場合があります。 

## <a name="where-phone-numbers-are-managed"></a>電話番号を管理する場所

番号を管理する場所と方法は、PSTN 接続オプションによって異なります。

- Microsoft 通話プランとオペレーター接続の電話番号は、Microsoft 365 でのみ管理できます。

- ダイレクト ルーティングの電話番号は、次のセクションで説明するように、オンプレミスの Active Directoryまたは Microsoft 365 で管理できます。

### <a name="direct-routing-numbers-managed-in-an-on-premises-active-directory"></a>オンプレミスの Active Directoryで管理されるダイレクト ルーティング番号

Skype for Business Serverハイブリッド展開がある場合や、オンプレミスの Active Directoryが Microsoft 365 と同期している可能性が高くなります。 つまり、ユーザー アカウントとリソース アカウントのディレクトリ属性は、オンプレミスの Active Directoryで管理され、Microsoft 365 に同期されます。

ダイレクト ルーティング電話番号がオンプレミスの Active Directoryのユーザー またはリソース アカウントで管理されている場合、アカウントの msRTCSIP-Line パラメーターに値が含まれます。 ADSI Edit などのツールを使用すると、ダイレクト ルーティングの電話番号がオンプレミスの Active Directoryに割り当てられているユーザーまたはリソース アカウントの msRTCSIP-Line パラメーターを表示できます。   

このパラメーターがディレクトリ同期プロセス (Azure AD Connect) を通じて Microsoft 365 のユーザーまたはリソース アカウントに自動的に同期された後、 [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) コマンドレットからの出力で OnPremLineURi パラメーターを調べて電話番号を表示できます。

| どこ | パラメーター | 値 |
| :------------| :-------| :---------|
| オンプレミス AD | msRTCSIP-Line | tel:+14255551234 |
| Microsoft 365 | OnPremLineURi | tel:+14255551234 |

### <a name="direct-routing-numbers-managed-in-microsoft-365"></a>Microsoft 365 で管理されているダイレクト ルーティング番号

オンプレミスの Active Directoryでダイレクト ルーティングの電話番号を管理していない場合は、Microsoft 365 で管理されます。 電話番号は Microsoft 365 と同期されていないため、ユーザーまたはリソース アカウントに対して実行されるGet-CsOnlineUser コマンドレットからの出力の OnPremLineUri パラメーターには表示されません。

### <a name="direct-routing-numbers-managed-in-both-an-on-premises-active-directory-and-microsoft-365"></a>オンプレミスの Active Directoryと Microsoft 365 の両方で管理されるダイレクト ルーティング番号

Microsoft 365 では、オンプレミスの Active Directory内の一部のユーザーアカウントとリソース アカウントのダイレクト ルーティング電話番号と、他のアカウントのダイレクト ルーティング電話番号を管理できます。 この機能は、属性 msRTCSIP-Line がオンプレミスの Active Directoryのユーザー アカウントまたはリソース アカウントに設定されているかどうかによって異なります。    

### <a name="change-where-direct-routing-phone-numbers-are-managed"></a>ダイレクト ルーティングの電話番号を管理する場所を変更する

ダイレクト ルーティング電話番号を管理する場所を変更するには、ユーザーの msRTCSIP-Line 属性から電話番号を削除するか、オンプレミスの Active Directoryのアカウントを resouce にする必要があります。   

詳細については、「[Active Directory 内のすべてのオンプレミス ユーザーのSkype for Business属性をクリアする」を](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory.md)参照してください。 電話番号は、Microsoft 365 のユーザーまたはリソース アカウントに再割り当てる必要があることに注意してください。

削除が Microsoft 365 に同期されると、ユーザーまたはリソース アカウントのGet-CsOnlineUserからの出力の OnPremLineUri 属性は空になります。 

