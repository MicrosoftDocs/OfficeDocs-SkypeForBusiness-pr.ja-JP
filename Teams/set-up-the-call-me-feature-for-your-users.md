---
title: ユーザーの [電話する] 機能をセットアップする
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: ユーザーが自分のコンピューターを音声に使用するときに電話で音声部分に参加できない可能性がある場合に、Teams の [自分に電話で知り合い] 機能を設定する方法について学習します。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b78edc01f68df19e850a85eb0ffa99163b9edae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821097"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>ユーザーの [電話する] 機能をセットアップする

Microsoft Teams の通話機能 **を使用** すると、電話で会議の音声部分に参加できます。 これは、コンピューターを使用してオーディオを使用できない場合に便利です。 ユーザーは、携帯電話または固定電話を通じて会議の音声部分を取得し、別の会議参加者が自分の画面を共有したり、自分のコンピューターを介してビデオを再生したりした場合など、会議のコンテンツ部分を &mdash; &mdash; 取得します。

> [!IMPORTANT]
> 
> (新型コロナウイルス感染症の発生で) 会議の数が多い間は、ユーザーは PSTN 会議番号を使用または<strong>[折り返し先]</strong>を使用してダイヤルインするのではなく、<strong>[Teams 会議に参加]</strong>ボタンをクリックして会議に参加することをお勧めします。 これにより、会議の数が多いことが PSTN ネットワークの混雑の原因となっているときに、音質を高められます。 

> [!IMPORTANT]
> 新型コロナウイルス感染症 (COVID-19) の発生が起こっている間、PSTN 会議番号を使用または **[折り返し先]** を使用してダイヤルインするのではなく、**[Teams 会議に参加]** ボタンをクリックして、ユーザーが会議に参加することをお勧めします</strong>。 これは主に、COVID-19 の影響を受ける国のテレフォニー インフラストラクチャが混雑するためです。 PSTN 通話を回避することによって、音質が向上します。 

## <a name="the-user-experience"></a>ユーザー エクスペリエンス

### <a name="join-a-meeting-by-using-phone-for-audio"></a>音声に電話を使って会議に参加する

[**参加]** をクリックして会議に参加し、[音声とビデオの設定の選択] 画面で [**電話の音声] をクリック** します。 ここから、ユーザーは会議の電話を受け、会議に参加したり、会議に手動でダイヤルインできます。

![電話の音声オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Teams 会議の通話を行う**

[音声 **に電話を使** う] 画面で、ユーザーが自分の電話番号を入力し、[電話を受け取る] を **クリックします**。 会議によってユーザーが呼び出され、会議に参加します。

![[電話をオーディオ画面に使う] の [電話で呼び出す] オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**手動でダイヤルインする**

参加するもう 1 つの方法は、会議に直接ダイヤルインする方法です。 [音声 **に電話を使う**]画面で、[手動でダイヤルイン] をクリックして、会議にダイヤルインするために使用する電話番号の一覧を取得します。

![[手動でダイヤルイン] オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>会議中に音声に問題が発生した場合に通話を取り戻す

ユーザーが会議中にコンピューターを使用するときに音声の問題が発生した場合、ユーザーは簡単に自分の電話を音声に切り替えます。 Teams は、音声またはデバイスの問題が発生した場合を検出し、[戻る] オプションを表示してユーザーに電話を使用 **をリダイレクト** します。

Teams がマイクを検出しない場合に表示されるメッセージと [電話で戻る] オプションの例を次に示します。

![[戻る] オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

ユーザーが [電話で **戻る**] をクリックすると、[電話を音声で使う] **画面が表示** されます。 ここから、電話番号を入力し、Teams 会議通話を受け、会議に参加するか、会議に手動でダイヤルインします。

## <a name="set-up-the-call-me-feature"></a>通話機能を設定する

組織内のユーザーに対して [呼び出し] 機能を有効にするには、次を構成する必要があります。

- 電話会議は、会議をスケジュールする組織内のユーザー (会議の開催者) に対して有効になります。 詳細については、「Teams の電話会議のセットアップ」および [「Teams](set-up-audio-conferencing-in-teams.md) でユーザーの電話会議設定 [を管理する」を参照してください](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

- ユーザーは会議からダイヤルアウトできます。 詳細については、「Teams でユーザー [の電話会議設定を管理する」を参照してください](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

ユーザーが会議からダイヤルアウトを有効にしない場合、[呼び出し] オプションは使用できないので、ユーザーは会議に参加する呼び出しを受信しません。 代わりに、[電話を音声に使う] 画面に電話番号の一覧が表示されます。この一覧を使って、電話で会議に手動でダイヤルインできます。
