---
title: 電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理者は、ユーザーが発信できる電話会議とエンドユーザーの PSTN 通話の種類を制御できます。
ms.openlocfilehash: e4589a2785d5debf4de6d6a146ede76b020cd2d6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299155"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー

管理者は、発信通話の制御を使用して、組織内のユーザーが発信できる電話会議の種類とエンド ユーザーの PSTN 通話を制限できます。 

発信通話コントロールは、ユーザー単位で適用できます。また、次の2つのコントロールを使用して、各送信通話の種類を個別に制限することができます。 既定では、両方のコントロールが国際通話と国内送信通話を許可するように設定されています。 

|リモコン|説明|コントロールオプション|
|:-----|:-----|:-----|
|電話会議の PSTN 通話|送信の種類を制限します </br>で許可されている通話 </br>ユーザーによって開催された会議。|国際および国内 (既定)</br>市外</br>なし|
|エンドユーザーによる PSTN 通話|通話の種類を制限する </br>これはユーザーが行うことができます。|国際および国内 (既定)</br>市外</br>なし|

   > [!NOTE]
   > 発信365先の電話番号が、会議の開催者 (電話会議の場合) またはエンドユーザー (エンドユーザーの PSTN 通話の場合) に設定されている国と同じ国にある場合、通話は国内と見なされます。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>電話会議の発信通話を制限する 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部にある [**編集**] をクリックします。

3. [**電話会議**] の横の [**編集**] をクリックします。

4. [**会議からのダイヤルアウトアクセス許可**] で、目的のダイヤルアウト制限オプションを選びます。

5. [**保存**] をクリックします。 

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する**

1.  **Skype for business 管理センター**の左のナビゲーションで、[**電話会議** > **ユーザー**] に移動し、利用可能なユーザーのリストからユーザーを選びます。

2.  操作ウィンドウで、[ **編集**] をクリックします。

3.  [**このユーザーの会議からのダイヤル**アウトの制限] で、目的のダイヤルアウト制限オプションを選びます。

    ![ダイヤルアウトオプションの制限](../images/restrictions-to-dial-outs.png)

5. [**保存**] をクリックします。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**PowerShell を使用する**

発信通話の制限は、それぞれの制限属性を持つ OnlineDialOutPolicy という1つのポリシーによって制御されます。 ポリシーをカスタマイズすることはできません。設定の各組み合わせに対して事前に定義されたポリシーインスタンスがあります。 

Get-Csonlinaloutpolicy コマンドレットを使用して、発信通話ポリシーを表示し、アクセス許可を付与してユーザーに割り当てることができます。 (Grant コマンドレットには、Get コマンドレットの場合、"Online" という単語が含まれていないことに注意してください)。 

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
