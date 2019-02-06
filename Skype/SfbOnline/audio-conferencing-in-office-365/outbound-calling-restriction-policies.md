---
title: 電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理者は、オーディオ会議、エンド ・ ユーザー PSTN の呼び出しのユーザーが可能なタイプを制御できます。
ms.openlocfilehash: 97df093168e896eabbc210545d516f386e1a6d25
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753474"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー

管理者は、オーディオ会議、エンド ・ ユーザー PSTN の呼び出し、組織内のユーザーが作成できるの種類を制限するのには、発信呼び出しコントロールを使用できます。 

発信通話コントロールは、ユーザーごとに適用することができ、発信呼び出しの種類を個別に制限するのには次の 2 つのコントロールを提供します。 既定では、両方のコントロールは、国際および国内の送信呼び出しを許可に設定されます。 

|コントロール|説明|コントロール オプション|
|:-----|:-----|:-----|
|オーディオ会議の PSTN の呼び出し|送信の種類を制限します。 </br>内で許可されている呼び出し </br>ユーザーが開催するミーティングです。|国際および国内 (既定値)</br>国内</br>なし|
|エンド ・ ユーザーの PSTN の呼び出し|呼び出しの種類を制限します。 </br>ユーザーが可能です。|国際および国内 (既定値)</br>国内</br>なし|

   > [!NOTE]
   > 呼び出しは、国内の場合は、開催者の会議 (オーディオ会議) の場合、またはエンド ・ ユーザー (エンド ・ ユーザーの PSTN 通話) の場合に Office 365 に設定されている国の国と同じでは、呼び出し先の電話番号が決定されます。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>オーディオ会議の発信を制限します。 

![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. **オーディオ会議**の横にある [**編集**] をクリックします。

4. **会議からの発信アクセス許可**を [ダイヤルアウトの制限オプションを選択を選択します。

5. [**保存**] をクリックします。 

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**

1.  **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **のユーザー**、および利用可能なユーザーの一覧からユーザーを選択します。

2.  操作ウィンドウで、[ **編集**] をクリックします。

3.  [**ダイヤル アウトこのユーザーの会議からへの制限**、ダイアル アウトの制限オプションを選択を選択します。

    ![ダイアル アウトのオプションを制限](../images/restrictions-to-dial-outs.png)

5. [**保存**] をクリックします。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**PowerShell を使用します。**

発信制限は、それぞれの制限属性を持っている OnlineDialOutPolicy と呼ばれる 1 つのポリシーによって制御されます。 ポリシーをカスタマイズすることはできませんではなく、設定の各組み合わせに対して事前に定義されたポリシーのインスタンスがあります。 

Get CSOnlineDialOutPolicy コマンドレットを使用すると発信の呼び出し元のポリシーを表示し、補助金 CSDialOutPolicy コマンドレットを使用してユーザーに割り当てることができます。 (注意: Grant コマンドレット含まれていないこと、単語「オンライン」Get コマンドレットのよう。) 

次の表は、各ポリシーの概要を示します。

|||
|:-----|:-----|
|Id =' タグ: DialoutCPCandPSTNInternational'    |    会議内で、ユーザーが国際と国内の番号にダイアル アウトができるし、このユーザーは、国際および国内の番号に発信呼び出しを行うもできます。    |
|Id =' タグ: DialoutCPCDomesticPSTNInternational'  |    会議内のユーザー、国内の番号にダイヤルアウトのみ、このユーザーは、国際および国内の番号に発信呼び出しを行うことができます。    |
|    Id =' タグ: DialoutCPCDisabledPSTNInternational'    |    会議内のユーザー任意のダイヤルを作成できません。このユーザーには、国際および国内の番号に発信呼び出しを行うことができます。    |
|    Id =' タグ: DialoutCPCInternationalPSTNDomestic'    |    会議内で、ユーザーが国際と国内の番号にダイアル アウトができるし、このユーザーは、国内の PSTN 番号に発信呼び出しを行うだけことができます。    |
|    Id =' タグ: DialoutCPCInternationalPSTNDisabled'    |    会議内で、ユーザーが国際と国内の番号にダイアル アウトができるし、このユーザーは、緊急時の番号だけでなく、PSTN 番号に送信通話をすることはできません。    |
|    Id =' タグ: DialoutCPCandPSTNDomestic'    |    会議内のユーザー、国内の番号にダイヤルアウトのみ、このユーザーは国内の PSTN 番号に発信呼び出しのみを作成できます。    |
|    Id =' タグ: DialoutCPCDomesticPSTNDisabled'    |    会議内のユーザー、国内の番号にダイヤルアウトのみ、このユーザーは、緊急時の番号だけでなく、PSTN 番号に送信通話をすることはできません。    |
|    Id =' タグ: DialoutCPCDisabledPSTNDomestic'    |    会議内のユーザーは、任意のダイヤルを行うことはできませんし、このユーザーは国内の PSTN 番号に発信呼び出しのみを作成できます。    |
|    Id =' タグ: DialoutCPCandPSTNDisabled'    |    会議内のユーザーは、任意のダイヤルを行うことはできませんし、このユーザーは、緊急時の番号だけでなく、PSTN 番号に送信通話をすることはできません。    |
