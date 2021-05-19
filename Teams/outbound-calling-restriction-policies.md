---
title: 発信通話の制限 - PSTN 通話&電話会議
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
description: 管理者は、ユーザーが行える電話会議とエンドユーザー PSTN 通話の種類を制御できます。
ms.openlocfilehash: 86622b493fbb8d31f98f600acb7158afc82e15e5
ms.sourcegitcommit: 02703e8f9a512848e158a3a4f38d84501ad5f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52526730"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー

管理者は、発信通話コントロールを使用して、組織内のユーザーが行える電話会議とエンドユーザーの公衆交換電話網 (PSTN) 通話の種類を制限できます。

発信呼び出しコントロールは、ユーザー単位またはテナント単位で適用できます。次の 2 つのコントロールを提供して、各種類の送信呼び出しを個別に制限します。 既定では、両方のコントロールが、国際および国内の発信呼び出しを許可する設定になっています。

|コントロール|説明|コントロール オプション|
|:-----|:-----|:-----|
|電話会議 PSTN 通話|送信の種類を制限します。 </br>内から許可されている呼び出し </br>ユーザーが開催した会議。|任意の宛先 (既定)</br>開催者と同じ国または地域 </br> [ゾーン A の国または地域のみ](audio-conferencing-zones.md) </br>許可しない|
|エンドユーザーの PSTN 通話|呼び出しの種類を制限します。 </br>ユーザーが作成できます。|国際および国内 (既定)</br>国内</br>なし|

ゾーン A と見なされる国と地域を確認するには、「電話会議の国と [地域のゾーン」を参照してください](audio-conferencing-zones.md)。

   > [!NOTE]
   > ダイヤルされた番号が会議の開催者 (電話会議の場合) またはエンド ユーザー (エンド ユーザー PSTN 通話の場合) に設定されている Office 365 Microsoft 365国と同じ国にある場合、通話は国内と見なされます。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>電話会議の発信通話を制限する

![[Microsoft Teams 管理 ](media/teams-logo-30x30.png) **センターを使用Microsoft Teamsロゴ**

1. 左側のナビゲーションで [ユーザー] **を選択** し、使用可能なユーザーの一覧からユーザーの表示名を選択します。

3. [電話会議 **] の横にある [** 編集] を **選択します**。

4. [ **会議からのダイヤルアウト] で**、必要なダイヤルアウト制限オプションを選択します。

5. **[保存]** を選択します。

![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

1. [Skype for Business **管理** センター] の左側のナビゲーションで、[電話会議ユーザー ] に移動し、使用可能なユーザーの一覧からユーザー  >  を選択します。

2. [操作] ウィンドウで、[編集] を **選択します**。

3.  [ **このユーザーの会議からの** ダイヤルアウトの制限] で、必要なダイヤルアウト制限オプションを選択します。

      ![[ダイヤルアウトの制限] オプション](media/restrictions-to-dial-outs.png)

4. **[保存]** を選択します。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**PowerShell を使用する場合**

発信呼び出し制限は、OnlineDialOutPolicy と呼ばれる 1 つのポリシーによって制御されます。このポリシーには、それぞれに制限属性があります。 ポリシーをカスタマイズすることはできません。設定の組み合わせごとに事前に定義されたポリシー インスタンスがあります。

Get-CSOnlineDialOutPolicy コマンドレットを使用して、発信呼び出しポリシーを表示し、セットアップに次のコマンドを使用できます。

**次のコマンドレットを使用して、ユーザーレベルでポリシーを設定します**。 (Grant コマンドレットには、Get コマンドレットと同様に "Online" という単語が含まれている必要があります)。

```
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**次のコマンドレットを使用して、テナント レベルでポリシーを設定します**。

```
Grant-CsDialoutPolicy  -Tenant <guid> -PolicyName <policy name>  -Global 
```

ダイヤルアウト ポリシーが割り当てられていないテナントのすべてのユーザーに、このポリシーが適用されます。 他のユーザーは、現在のポリシーのままです。

次の表は、各ポリシーの概要を示しています。

|PowerShell コマンドレット|説明|
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    会議のユーザーは、国際電話番号と国内番号にダイヤルアウトできます。また、このユーザーは、国際電話番号と国内番号への発信通話を行う場合にも使用できます。    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    会議のユーザーは国内番号にのみダイヤルアウトできます。このユーザーは、国際番号と国内番号への発信通話を行います。    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    会議のユーザーがダイヤルアウトできない。このユーザーは、国際番号と国内番号への発信呼び出しを行います。    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    会議のユーザーは国際番号と国内番号にダイヤルアウトできます。このユーザーは国内 PSTN 番号への発信通話のみを行います。    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    会議のユーザーは国際番号と国内番号にダイヤルアウトできます。このユーザーは、緊急電話番号以外に PSTN 番号への発信通話を行う必要があります。    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    会議のユーザーは国内番号にのみダイヤルアウトできます。このユーザーは国内 PSTN 番号への発信通話のみを行います。    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    会議のユーザーは国内番号にのみダイヤルアウトできます。このユーザーは、緊急電話番号以外に PSTN 番号への発信通話を行う必要があります。    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    会議のユーザーはダイヤルアウトできないので、このユーザーは国内 PSTN 番号への発信通話のみを行います。    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    会議のユーザーはダイヤルアウトできないので、このユーザーは緊急電話番号以外に PSTN 番号への発信通話を行う必要があります。    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    会議のユーザーはゾーン [A](audio-conferencing-zones.md)の国と地域にのみダイヤルアウトできます。このユーザーは、国際番号と国内番号への発信通話を行います。    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    会議のユーザーはゾーン [A](audio-conferencing-zones.md)の国と地域にのみダイヤルアウトできます。このユーザーは国内 PSTN 番号への発信通話のみを行います。    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    会議のユーザーはゾーン [A](audio-conferencing-zones.md)の国と地域にのみダイヤルアウトできます。このユーザーは、緊急電話番号以外に PSTN 番号への発信呼び出しを行う必要があります。    |
