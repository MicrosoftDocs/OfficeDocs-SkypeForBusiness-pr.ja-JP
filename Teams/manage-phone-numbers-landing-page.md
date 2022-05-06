---
title: 組織のために電話番号を管理する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
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
description: 組織のMicrosoft Teamsのユーザー (サブスクライバー) とサービス (有料および無料) の電話番号を取得および管理する方法について説明します。
ms.openlocfilehash: c4ea749e98097765d302c334f5d8bd75e8dc0d21
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763811"
---
# <a name="manage-telephone-numbers-for-your-organization"></a>組織の電話番号を管理する

現在、Microsoft では次の 2 つの電話番号の種類がサポートされています。 

- [**ユーザー番号**](#user-telephone-numbers)はサブスクライバー番号とも呼ばれ、組織内のユーザーに割り当てることができます。

- 電話会議、[自動応答](plan-auto-attendant-call-queue.md)、[通話キュー](plan-auto-attendant-call-queue.md)[などのサービス](deploy-audio-conferencing-teams-landing-page.md)に割り当てられる [**サービス番号**](#service-telephone-numbers)。

Microsoft は数値型の簡略化に取り組んでいますが、現時点では次のことを決定する必要があります。

- Microsoft から新しい電話番号が必要なユーザーの場所はどれですか?
- どの種類の電話番号が必要ですか (サブスクライバーまたはサービス)?
- 既存の電話番号操作方法Teamsに移植しますか?

電話番号を取得および管理する方法は、PSTN 接続オプションによって異なります。

- Microsoft 通話プランの電話番号の管理については、「通話プラン [の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。

- オペレーター接続の電話番号の管理の詳細については、「[オペレーター接続を使用して電話番号を設定](operator-connect-configure.md#set-up-phone-numbers)する」を参照してください。

- ダイレクト ルーティングの電話番号の管理の詳細については、「電話番号 [を構成し、エンタープライズ音声を有効にする](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice)」を参照してください。

Microsoft Teams管理センターに表示されている番号以外の追加または他の番号の種類が必要な場合は、[電話番号サービス センター](https://pstnsd.powerappsportals.com/)に電話番号の要求を送信できます。

## <a name="user-telephone-numbers"></a>ユーザーの電話番号

組織内のユーザーに割り当てることができるユーザー電話番号には、次の 2 種類があります。  
    
- **地理的な数値** は地理的な領域との関係を持ち、最も一般的です。 たとえば、ほとんどの場合、地理的な電話番号は、国の特定の住所、都市、州、または地域内でのみ使用できます。
    
- **地理的でない数値** は、国番号または場合によっては VoIP 番号と呼ばれます。 これらの数値には、国/地域内の地理的領域との関係はありません。 たとえば、国/地域内の任意の場所から番号を呼び出すときに、非地理的な数値に同じコストがかかることがよくあります。 また、デンマークなどの一部の国では、地理的でない番号しか使用できません。


## <a name="service-telephone-numbers"></a>サービスの電話番号  

このセクションでは、ライセンスに含まれる Microsoft から入手できるサービス番号について説明します。 オペレーター接続またはダイレクト ルーティングによって提供されるサービス番号については、プロバイダーにお問い合わせください。 

Microsoft-Toll とフリーダイヤルによって提供されるサービス電話番号には、電話会議、自動応答、通話キューなどのサービスに割り当てることができる 2 種類のサービス電話番号があります。 サービス番号は、ユーザー番号よりも高い同時呼び出し容量を持っています。 サービス番号の可用性は、国/地域、番号の種類 (有料またはフリーダイヤルのどちらでも) によって異なります。 Microsoft の国/地域ごとのテレフォニー ライセンスによって、使用できる番号が決まります。
    
 - **有料サービス番号 - 有料サービス番号** には次の 2 種類があり、発信者に有料料金が発生する可能性があります。
    
   - **地域番号** 地理的な数値には、地理的領域とのリレーションシップがあります。 たとえば、ほとんどの場合、地理的な電話番号は、国の特定の住所、都市、州、または地域内でのみ使用できます。
        
   - **地理的でない数値** 非地理的数値は、国/地域内の地理的領域との関係を持たない国番号です。 たとえば、国/地域内の任意の場所から番号を呼び出すときに、非地理的な数値に同じコストがかかることがよくあります。
   
- **無料サービス番号** - これらのサービス番号は、通常、呼び出し元に有料料金は発生しません。 Teamsは、60 を超える国/地域で国内のフリーダイヤル番号を提供しています。
    
    > [!CAUTION]
    > 一部の国/地域や発信番号の種類 (携帯電話から発信された通話など) では、発信者に有料料金が発生する場合があります。 


    
  
> [!NOTE]
> これより多くの電話番号を取得する必要がある場合は、[電話番号サービス センター](https://pstnsd.powerappsportals.com/)にお問い合わせください。