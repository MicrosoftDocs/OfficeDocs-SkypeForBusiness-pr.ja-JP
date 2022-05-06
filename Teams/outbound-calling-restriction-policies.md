---
title: 発信通話の制限 - 電話会議& PSTN 通話
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 管理者は、ユーザーが行うことができる電話会議とエンド ユーザーの PSTN 通話の種類を制御できます。
ms.openlocfilehash: 39a51c1fdf6bbb7597b255fc5879a4d7a77be2db
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055177"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー

管理者は、発信通話制御を使用して、組織内のユーザーが行うことができる電話会議とエンド ユーザーの公衆交換電話網 (PSTN) 呼び出しの種類を制限できます。

送信呼び出し制御は、ユーザー単位またはテナント単位で適用でき、次の 2 つのコントロールを提供して、送信呼び出しの種類ごとに個別に制限できます。 既定では、両方のコントロールが国際通話と国内発信通話を許可するように設定されています。

|コントロール|説明|コントロール オプション|
|:-----|:-----|:-----|
|電話会議 PSTN 通話|送信の種類を制限します </br>内から許可されている呼び出し </br>ユーザーが編成した会議。|任意の宛先 (既定値)</br>開催者と同じ国または地域 </br> [ゾーン A の国または地域](audio-conferencing-zones.md) のみ </br>許可しない|
|エンド ユーザー PSTN 通話|呼び出しの種類を制限します </br>ユーザーが作成できる。|国際および国内 (既定値)</br>国内</br>なし|

ゾーン A と見なされる国と地域については、「 [電話会議の国と地域のゾーン](audio-conferencing-zones.md)」を参照してください。

   > [!NOTE]
   > ダイヤルされた番号が、会議の開催者 (電話会議の場合) またはエンド ユーザー (エンド ユーザー PSTN 通話の場合) にMicrosoft 365またはOffice 365が設定されているのと同じ国にある場合、通話は国内と見なされます。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>電話会議の発信通話を制限する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで [ **ユーザー**] を選択し、使用可能なユーザーの一覧からユーザーの表示名を選択します。

2. 次に **、電話会議** に移動し、[ **編集]** を選択します。

3. [ **会議からのダイヤルアウト**] で、必要なダイヤルアウト制限オプションを選択します。

4. **[保存]** を選択します。

### <a name="using-powershell"></a>PowerShell の使用

送信呼び出しの制限は、OnlineDialOutPolicy という名前の 1 つのポリシーによって制御されます。それぞれに制限属性があります。 ポリシーはカスタマイズできません。設定の組み合わせごとに定義済みのポリシー インスタンスがあります。

Get-CSOnlineDialOutPolicy コマンドレットを使用して送信呼び出しポリシーを表示し、セットアップに次のコマンドを使用できます。

**次のコマンドレットを使用して、ユーザーごとのレベルでポリシーを設定** します。 (Grant コマンドレットには、Get コマンドレットと同じように "Online" という単語は含まれません。

```powershell
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**次のコマンドレットを使用して、テナント レベルでポリシーを設定します**。

```powershell
Grant-CsDialoutPolicy -PolicyName <policy name>  -Global 
```

ダイヤルアウト ポリシーが割り当てられていないテナントのすべてのユーザーは、このポリシーを取得します。 他のユーザーは現在のポリシーのままです。

**次のコマンドレットを使用して、テナント レベルで現在のポリシーを確認** します。

```powershell
Get-CSOnlineDialOutPolicy -Identity Global
```

次の表に、各ポリシーの概要を示します。

|PowerShell コマンドレット|説明|
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    会議のユーザーは国際番号と国内番号にダイヤルアウトでき、このユーザーは国際番号と国内番号への発信通話を行うこともできます。    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    会議のユーザーは国内番号にのみダイヤルアウトでき、このユーザーは国際番号と国内番号への発信通話を行うことができます。    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    会議のユーザーはダイヤルアウトできません。このユーザーは、国際番号と国内番号に対して発信通話を行うことができます。    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    会議のユーザーは国際番号と国内番号にダイヤルアウトでき、このユーザーは国内 PSTN 番号に対してのみ発信通話を行うことができます。    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    会議のユーザーは国際番号と国内番号にダイヤルアウトでき、このユーザーは緊急電話番号以外に PSTN 番号への発信通話を行うことはできません。    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    会議のユーザーは国内番号にのみダイヤルアウトでき、このユーザーは国内 PSTN 番号に対してのみ発信通話を行うことができます。    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    会議のユーザーは国内番号にのみダイヤルアウトでき、このユーザーは緊急電話番号以外に PSTN 番号への発信通話を行うことはできません。    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    会議のユーザーはダイヤルアウトできず、このユーザーは国内 PSTN 番号に対してのみ発信通話を行うことができます。    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    会議のユーザーはダイヤルアウトできず、このユーザーは緊急電話番号以外に PSTN 番号への発信通話を行うことはできません。    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    会議のユーザーは [ゾーン A の国と地域](audio-conferencing-zones.md)にのみダイヤルアウトでき、このユーザーは国際番号と国内番号への発信通話を行うことができます。    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    会議のユーザーは [ゾーン A の国と地域](audio-conferencing-zones.md)にのみダイヤルアウトでき、このユーザーは国内 PSTN 番号への発信通話のみを行うことができます。    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    会議のユーザーは [ゾーン A の国と地域](audio-conferencing-zones.md)にのみダイヤルアウトでき、このユーザーは緊急電話番号以外に PSTN 番号への発信通話を行うことはできません。    |
