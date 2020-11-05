---
title: 発信通話制限-電話会議 & PSTN 通話
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 管理者は、ユーザーが発信できる電話会議とエンドユーザーの PSTN 通話の種類を制御できます。
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908656"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー

管理者は、発信通話の制御を使用して、組織内のユーザーが発信できる電話会議の種類とエンド ユーザーの PSTN 通話を制限できます。 

発信通話コントロールは、ユーザー単位で適用できます。また、次の2つのコントロールを使用して、各送信通話の種類を個別に制限することができます。 既定では、両方のコントロールが国際通話と国内送信通話を許可するように設定されています。 

|リモコン|説明|コントロールオプション|
|:-----|:-----|:-----|
|電話会議の PSTN 通話|送信の種類を制限します </br>で許可されている通話 </br>ユーザーによって開催された会議。|任意の場所 (既定)</br>開催者と同じ国または地域 </br> [国または地域のみをゾーンにする](audio-conferencing-zones.md) </br>許可しない|
|エンドユーザーによる PSTN 通話|通話の種類を制限する </br>これはユーザーが行うことができます。|国際および国内 (既定)</br>市外</br>なし|

Zone A と見なされている国と地域を確認するには、「 [電話会議の国と地域のゾーン](audio-conferencing-zones.md)」を参照してください。

   > [!NOTE]
   > 発信 365 365 先の番号が、会議の開催者 (電話会議の場合) またはエンドユーザー (エンドユーザーの PSTN 通話の場合) に設定されている国と同じ国である場合、通話は国内と見なされます。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>電話会議の発信通話を制限する

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで [ **ユーザー** ] をクリックし、利用可能なユーザーのリストからユーザーの表示名をクリックします。

3. [ **電話会議** ] の横の [ **編集** ] をクリックします。

4. [ **会議からのダイヤルアウト** ] で、目的のダイヤルアウト制限オプションを選びます。

5. [ **保存** ] をクリックします。 

![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

1. **Skype for business 管理センター** の左のナビゲーションで、[ **電話会議**  >  **ユーザー** ] に移動し、利用可能なユーザーのリストからユーザーを選びます。

2. 操作ウィンドウで、[ **編集** ] をクリックします。

3.  [ **このユーザーの会議からのダイヤル** アウトの制限] で、目的のダイヤルアウト制限オプションを選びます。

      ![ダイヤルアウトオプションの制限](media/restrictions-to-dial-outs.png)
      

4. [ **保存** ] をクリックします。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**PowerShell を使用する場合**

発信通話の制限は、それぞれの制限属性を持つ OnlineDialOutPolicy という1つのポリシーによって制御されます。 ポリシーをカスタマイズすることはできません。設定の各組み合わせに対して事前に定義されたポリシーインスタンスがあります。 

Get-CSOnlineDialOutPolicy コマンドレットを使用して、発信通話ポリシーを表示し、Grant-CSDialOutPolicy コマンドレットを使用してユーザーに割り当てることができます。 (Grant コマンドレットには、Get コマンドレットの場合、"Online" という単語が含まれていないことに注意してください)。 

次の表は、各ポリシーの概要を示しています。

|||
|:-----|:-----|
|Identity = ' tag: DialoutCPCandPSTNInternational '    |    電話会議に参加しているユーザーは、国際電話や国内の番号にダイヤルアウトすることができます。このユーザーは、国際電話と国内の番号に発信することもできます。    |
|Identity = ' tag: DialoutCPCDomesticPSTNInternational '  |    電話会議のユーザーは国内電話番号へのダイヤルアウトのみを行うことができ、このユーザーは国際電話番号と国内電話番号への発信通話を行うことができます。    |
|    Identity = ' tag: DialoutCPCDisabledPSTNInternational '    |    会議に参加しているユーザーは、ダイヤルアウトを行うことができません。このユーザーは、国際電話番号と国内電話番号への発信通話を行うことができます。    |
|    Identity = ' tag: DialoutCPCInternationalPSTNDomestic '    |    電話会議に参加しているユーザーは、国際電話番号にダイヤルアウトすることができ、このユーザーは国内の PSTN 番号に対してのみ発信通話を発信できます。    |
|    Identity = ' tag: DialoutCPCInternationalPSTNDisabled '    |    電話会議に参加しているユーザーは、国際電話番号や国内電話にダイヤルアウトすることができます。このユーザーは、緊急電話番号以外の PSTN 番号への発信通話を行うことはできません。    |
|    Identity = ' tag: DialoutCPCandPSTNDomestic '    |    電話会議のユーザーは国内の電話番号にのみダイヤルアウトできます。このユーザーは国内の PSTN 番号に対してのみ発信通話を発信できます。    |
|    Identity = ' tag: DialoutCPCDomesticPSTNDisabled '    |    電話会議に参加しているユーザーは、国内電話番号へのダイヤルアウトのみを行うことができます。このユーザーは、緊急電話番号以外の PSTN 番号への発信通話を行うことはできません。    |
|    Identity = ' tag: DialoutCPCDisabledPSTNDomestic '    |    電話会議のユーザーはダイヤルアウトを行うことができず、このユーザーは国内の PSTN 番号に対してのみ発信通話を発信できます。    |
|    Identity = ' tag: DialoutCPCandPSTNDisabled '    |    電話会議のユーザーはダイヤルアウトを行うことができません。このユーザーは、緊急電話番号以外の PSTN 番号への発信通話を行うことはできません。    |
|    Identity = ' tag: ' の場合、'    |    電話会議のユーザーは、 [国と地域](audio-conferencing-zones.md)のみを対象としたダイヤルアウトを行うことができます。このユーザーは、国際および国内の電話番号に発信することができます。    |
|    Identity = ' tag: ' の場合は、次のようになります。    |    電話会議のユーザーは、 [国と地域](audio-conferencing-zones.md)のみを対象としたダイヤルアウトを行うことができます。このユーザーは、国内の PSTN 番号に対してのみ発信通話を発信できます。    |
|    Identity = ' tag: ' の場合は、次のようになります。    |    電話会議のユーザーは、 [国と地域](audio-conferencing-zones.md)のみを対象としたダイヤルアウトを行うことができます。このユーザーは、緊急電話番号以外の PSTN 番号への発信通話を行うことはできません。    |
