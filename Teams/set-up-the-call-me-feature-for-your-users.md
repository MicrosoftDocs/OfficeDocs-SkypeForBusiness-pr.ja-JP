---
title: ユーザーの [電話する] 機能をセットアップする
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: ユーザーがオーディオ用にコンピューターを使用しているときに、ユーザーが電話でオーディオ部分に参加できるように、Teams の [折り返し] 機能を設定する方法について説明します。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c2343ce76e404ce2462cdbfc443130058112dcc4
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140860"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>ユーザーの [電話する] 機能をセットアップする

Microsoft Teams の [**折り返し**] 機能を使用すると、ユーザーは電話で会議のオーディオ部分に参加することができます。 これは、オーディオ用のコンピューターを使うことができない場合に便利です。 ユーザーは、会議のオーディオ部分を、携帯電話または陸上線と、会議の他の参加者&mdash;が自分の画面を共有したり、コンピューターでビデオ&mdash;を再生したりする場合に、会議のコンテンツ部分を取得します。

> [!IMPORTANT]
> COVID-19 の感染期間中は、PSTN 会議の電話番号を使用するか、または [**折り返し**</strong>先] を使って、[ **Teams 会議への参加**] ボタンをクリックして、ユーザーが会議に参加することをお勧めします。 これは主に、COVID-19 によって影響を受ける国のテレフォニーインフラストラクチャの輻輳が原因です。 PSTN 通話を回避することで、音質が向上する可能性があります。 

## <a name="the-user-experience"></a>ユーザーエクスペリエンス

### <a name="join-a-meeting-by-using-phone-for-audio"></a>電話で音声を使って会議に参加する

会議に参加するには、[**参加**] をクリックし、[**オーディオとビデオの設定を選択して**ください] 画面で [電話の**オーディオ**] をクリックします。 ここでは、ユーザーが会議通話を使用して会議に参加したり、手動で会議にダイヤルインしたりすることができます。

![[電話] オーディオオプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**チームに会議通話を許可する**

[**オーディオ用に電話を使う**] 画面で、ユーザーは電話番号を入力し、[**折り返し**先] をクリックします。 会議はユーザーを呼び出し、会議に参加します。

![[オーディオ用電話を使う] 画面の [折り返し先] オプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**手動でダイヤルする**

もう1つの方法は、会議に直接ダイヤルインすることです。 [**オーディオ用に電話を使う**] 画面で、[**手動でダイヤル**する] をクリックして、会議にダイヤルインするために使用する電話番号の一覧を表示します。

![[手動でダイヤルする] オプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>会議中に音声で問題が発生した場合に、通話を取り戻す

ユーザーが会議中に自分のコンピューターを使っているときに音声の問題が発生した場合、ユーザーは簡単に電話で音声通話に切り替えることができます。 チームは、音声またはデバイスの問題が発生したときに検出し、[**コールバック**] オプションを表示して、ユーザーが電話を使用するようにユーザーをリダイレクトします。

ここでは、Teams でマイクが検出されないときに表示されるメッセージと [折り返して**戻る**] オプションの例を示します。

![[コールバック] オプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

ユーザーが [**コールバック**] をクリックすると、[**電話を使用する**] 画面が表示されます。 このページでは、自分の電話番号を入力して、Teams 会議に参加し、会議に直接参加したり、手動で会議にダイヤルインしたりすることができます。

## <a name="set-up-the-call-me-feature"></a>[折り返し先] 機能を設定する

組織内のユーザーに対して [折り返して呼び出す] 機能を有効にするには、次の設定を行う必要があります。

- 会議をスケジュールする組織内のユーザー (会議の開催者) では、電話会議が有効になっています。 詳細については、「 [teams の電話会議をセットアップ](set-up-audio-conferencing-in-teams.md)する」および「 [teams でユーザーの電話会議の設定を管理](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)する」を参照してください。

- ユーザーは会議からダイヤルアウトできます。 詳細については、「 [Teams でユーザーの電話会議の設定を管理](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)する」を参照してください。

ユーザーが会議からのダイヤルアウトを有効にしていない場合、 **[折り返し先] オプションは**利用できません。ユーザーは会議に参加するための電話を受けません。 代わりに、電話で電話の会議に手動でダイヤルインするために使うことができる電話番号のリストが、[**オーディオの使用電話**] 画面に表示されます。
