---
title: "オーディオ会議とユーザーの PSTN 通話の発信の呼び出し制限のポリシー"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 2/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "管理者は、オーディオ会議、エンド ・ ユーザー PSTN の呼び出しのユーザーが可能なタイプを制御できます。"
ms.openlocfilehash: 0585fc8861d8a805380bc6058523ec91087c4764
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2018
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>オーディオ会議とユーザーの PSTN 通話の発信の呼び出し制限のポリシー

管理者は、オーディオ会議、エンド ・ ユーザー PSTN の呼び出し、組織内のユーザーが作成できるの種類を制限するのには、発信呼び出しコントロールを使用できます。 

発信通話コントロールは、ユーザーごとに適用することができ、発信呼び出しの種類を個別に制限するのには次の 2 つのコントロールを提供します。 既定では、両方のコントロールは、国際および国内の送信呼び出しを許可に設定されます。 

|コントロール|説明|コントロール オプション|
|:-----|:-----|:-----|
|オーディオ会議の PSTN の呼び出し|送信の種類を制限します。 </br>内で許可されている呼び出し </br>ユーザーが開催するミーティングです。|国際および国内 (既定値)</br>国内</br>なし|
|エンド ・ ユーザーの PSTN の呼び出し|呼び出しの種類を制限します。 </br>ユーザーが可能です。|国際および国内 (既定値)</br>国内</br>なし|

   > [!NOTE]
   > 呼び出しは、国内の場合は、開催者の会議 (オーディオ会議) の場合、またはエンド ・ ユーザー (エンド ・ ユーザーの PSTN 通話) の場合に Office 365 に設定されている国の国と同じでは、呼び出し先の電話番号が決定されます。 


## <a name="restrict-audio-conferencing-outbound-calls-using-the-skype-for-business-admin-center"></a>ビジネス管理センターは、Skype を使用してオーディオ会議の送信呼び出しを制限します。 


1.  Go to the **Office 365 admin center** > **Skype for Business**.
2.  ビジネス管理センターでは、左側のナビゲーションでは、Skype で**電話会議**に移動する > **のユーザー**、および利用可能なユーザーの一覧からユーザーを選択します。
3.  In the Skype for Business admin center, in the left navigation go to Dial-in conferencing > Provider name drop-down, and then select the dial-in conferencing provider for the user.
4.  [**ダイヤル アウトこのユーザーの会議からへの制限**、ダイアル アウトの制限オプションを選択を選択します。

    ![ダイアル アウトのオプションを制限](../images/restrictions-to-dial-outs.png)

5. [ **保存**] をクリックします。

## <a name="restrict-audio-conferencing-and-end-user-outbound-calls-using-powershell"></a>PowerShell を使用する会議とエンド ・ ユーザー、送信呼び出しのオーディオを制限します。

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
