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
description: ユーザーが自分のコンピューターを使用して音声を使用できない場合に電話で音声部分に参加できるよう、Teams の [自分に電話で知り合い] 機能を設定する方法について学習します。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 04510a827e9343010c756b14590e9800354c71e9
ms.sourcegitcommit: f979c491af5210e6ceb1d1c00e000767f1a8311d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "51623135"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>ユーザーの [電話する] 機能をセットアップする

Microsoft Teams の通話機能 **を使** って、電話で会議の音声部分に参加できます。 これは、コンピューターを使用してオーディオを使用できない場合に便利です。 ユーザーは、携帯電話または固定電話を通じて会議の音声部分を取得し、別の会議参加者が自分の画面を共有したり、コンピューターを介してビデオを再生したりした場合など、会議のコンテンツ部分を &mdash; &mdash; 取得します。

> [!IMPORTANT]
> 
> (新型コロナウイルス感染症の発生で) 会議の数が多い間は、ユーザーは PSTN 会議番号を使用または<strong>[折り返し先]</strong>を使用してダイヤルインするのではなく、<strong>[Teams 会議に参加]</strong>ボタンをクリックして会議に参加することをお勧めします。 これにより、会議の数が多いことが PSTN ネットワークの混雑の原因となっているときに、音質を高められます。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>ユーザー エクスペリエンス

### <a name="join-a-meeting-by-using-phone-for-audio"></a>音声に電話を使って会議に参加する

[**参加]** をクリックして会議に参加し、[ビデオとオーディオのオプションの選択] 画面で音声を電話で送信し、[今すぐ参加] を **クリックします**。 ここから、ユーザーは会議の電話を受け、会議に参加したり、会議に手動でダイヤルインできます。

![電話の音声オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Teams 会議の通話を行う**

[音声 **に電話を使** う] 画面で、ユーザーは自分の電話番号を入力し、[電話を受け取る] を **クリックします**。 会議はユーザーを呼び出し、会議に参加します。

![[電話をオーディオ画面に使う] の [電話で呼び出す] オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**手動でダイヤルインする**

参加するもう 1 つの方法は、会議に直接ダイヤルインする方法です。 [音声 **に電話を使う**]画面で、[手動でダイヤルイン] をクリックして、会議にダイヤルインするために使用する電話番号の一覧を取得します。

![[手動でダイヤルイン] オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>会議中に音声に問題が発生した場合に通話を取り戻す

ユーザーが会議中にコンピューターを使用するときに音声の問題が発生した場合、ユーザーは簡単に自分の電話を音声に切り替えます。 Teams は、音声またはデバイスの問題が発生した場合を検出し、[戻る] オプションを表示してユーザーに電話を使用 **します** 。

Teams がマイクを検出しない場合に表示されるメッセージと [電話で戻る] オプションの例を次に示します。

![[戻る] オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

ユーザーが [電話で **戻る**] をクリックすると、[電話を音声で使う] **画面が表示** されます。 ここから、電話番号を入力し、Teams の会議通話を受け、会議に参加するか、会議に手動でダイヤルインします。

## <a name="set-up-the-call-me-feature"></a>通話機能を設定する

組織内のユーザーに対して [呼び出し] 機能を有効にするには、次を構成する必要があります。

- 電話会議は、会議をスケジュールする組織内のユーザー (会議の開催者) に対して有効になります。 詳細については、「Teams の電話会議のセットアップ」および [「Teams](set-up-audio-conferencing-in-teams.md) でユーザーの電話会議設定 [を管理する」を参照してください](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

- 会議の開催者は、会議からダイヤルアウトできます。 詳細については、「Teams でユーザーの電話会議設定を管理 [する」を参照してください](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

会議の開催者が会議からダイヤルアウトを有効にしない場合、[ビデオと音声のオプションの選択] 画面の [電話] 音声オプションは、誰も利用できません。また、他のユーザーは、会議に参加するための通話を受信できません。 ダイヤルアウトが有効になっているユーザーの場合、会議に参加すると、[参加者の表示] アイコンから他のユーザーが自分の番号をダイヤルして **参加** できます。
