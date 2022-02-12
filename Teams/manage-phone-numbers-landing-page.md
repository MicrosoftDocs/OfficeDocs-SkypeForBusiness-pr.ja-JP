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
description: 組織のユーザー (サブスクライバー) とサービス (有料および無料) の電話番号を取得および管理する方法Microsoft Teams確認します。
ms.openlocfilehash: c4ea749e98097765d302c334f5d8bd75e8dc0d21
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763811"
---
# <a name="manage-telephone-numbers-for-your-organization"></a>組織の電話番号を管理する

現在、Microsoft では次の 2 種類の電話番号をサポートしています。 

- [**ユーザー番号**](#user-telephone-numbers) (サブスクライバー番号とも呼ばれる) は、組織内のユーザーに割り当てることができます。

- [**電話会議**](#service-telephone-numbers)、自動応答、通話キューなどのサービス [](deploy-audio-conferencing-teams-landing-page.md)に割り当 [](plan-auto-attendant-call-queue.md)てられるサービス [番号](plan-auto-attendant-call-queue.md)。

Microsoft では、番号の種類を簡略化するために取り組していますが、今のところ、次の決定が必要です。

- Microsoft の新しい電話番号が必要なユーザーの場所
- どの種類の電話番号が必要ですか (サブスクライバーまたはサービス)?
- 既存の電話番号を電話番号に移植する方法Teams?

電話番号を取得および管理する方法は、PSTN 接続オプションによって異なります。

- Microsoft 通話プランの電話番号の管理については、「通話プランの電話番号を [管理する」を参照してください](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- オペレーター アカウントの電話番号の管理については、「オペレーターアカウントで電話番号を設定Connect」[を参照Connect](operator-connect-configure.md#set-up-phone-numbers)。

- ダイレクト ルーティングの電話番号の管理については、「電話番号を構成し、エンタープライズ音声を有効にする [」を参照してください](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice)。

Microsoft Teams 管理センターに表示される番号以外の番号の種類が必要な場合は、電話 [Number Service Center に電話番号要求を送信できます](https://pstnsd.powerappsportals.com/)。

## <a name="user-telephone-numbers"></a>ユーザーの電話番号

組織内のユーザーに割り当て可能なユーザー電話番号には、次の 2 種類があります。  
    
- **地理的な数値** は地理的な領域との関係を持ち、最も一般的です。 たとえば、ほとんどの場合、地理的な電話番号は、国の特定の住所、市区町町地域内でのみ使用できます。
    
- **地理以外の数値は** 、国内番号または VoIP 番号と呼ばれる場合があります。 これらの数値は、国/地域内の地理的領域との関係を持つ必要があります。 たとえば、国/地域内の任意の場所から番号を呼び出す場合、多くの場合、地理的でない数値のコストは同じです。 また、デンマークなどの一部の国では、地理的でない番号しか使用できません。


## <a name="service-telephone-numbers"></a>サービス電話番号  

このセクションでは、ライセンスに含まれる Microsoft から利用可能なサービス番号について説明します。 オペレーター サービスまたはダイレクト ルーティングによって提供されるサービスConnectプロバイダーにお問い合わせください。 

電話会議、自動応答、通話キューなどのサービスに割り当て可能な、Microsoft-toll と無料の 2 種類のサービス電話番号が提供されます。 サービス番号は、ユーザー番号よりも高い同時呼び出し容量を持っています。 サービス番号の利用可否は、国/地域と番号の種類によって異なります (有料または無料の番号の場合)。 各国/地域の Microsoft のテレフォニー ライセンスは、番号を使用できる内容を示します。
    
 - **有料サービス番号** - 2 種類の有料サービス番号があります。呼び出し元に料金が発生する可能性があります。
    
   - **地理的な番号** 地理的な数値は、地理的な領域と関係があります。 たとえば、ほとんどの場合、地理的な電話番号は、国の特定の住所、市区町町地域内でのみ使用できます。
        
   - **地理以外の数値** 地理的でない数値は、国/地域内の地理的な地域との関係を持つ国番号です。 たとえば、国/地域内の任意の場所から番号を呼び出す場合、多くの場合、地理的でない数値のコストは同じです。
   
- **無料サービス番号** - これらのサービス番号は、通常、発信者に有料のコストは発生しません。 Teams、60 を超える国/地域で国内の無料電話番号を提供しています。
    
    > [!CAUTION]
    > 携帯電話からの通話など、発信元の国/地域や発信元の番号の種類によっては、発信者への有料料金が発生する場合があります。 


    
  
> [!NOTE]
> これより多くの電話番号を取得する必要がある場合は、電話番号サービス センター電話[問い合わせください](https://pstnsd.powerappsportals.com/)。