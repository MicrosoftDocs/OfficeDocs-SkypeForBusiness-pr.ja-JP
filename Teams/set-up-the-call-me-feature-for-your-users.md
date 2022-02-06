---
title: 'ユーザーの [電話する] 機能をセットアップする'
author: SerdarSoysal
ms.author: serdars
ms.reviewer: 'macai, phedry'
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: コンピューターを使用して音声を使用できない場合に、ユーザーが電話で音声部分に参加できるよう、Teams で通話機能を設定する方法について学習します。
ms.localizationpriority: medium
ms.collection:
  - M365-voice
f1.keywords:
  - NOCSH
appliesto:
  - Microsoft Teams
ms.custom: seo-marvel-mar2020
---

# <a name="set-up-the-call-me-feature-for-your-users"></a>ユーザーの [電話する] 機能をセットアップする

このMicrosoft Teams通話 **機能** を使用すると、ユーザーは電話で会議の音声部分に参加できます。 これは、オーディオにコンピューターを使用できない場合に便利です。 ユーザーは、&mdash;&mdash;携帯電話または固定電話を介して会議の音声部分を取得し、別の会議参加者が自分の画面を共有したり、自分のコンピューターを介してビデオを再生したりする場合など、会議のコンテンツ部分を取得します。

> [!IMPORTANT]
> 
> (新型コロナウイルス感染症の発生で) 会議の数が多い間は、ユーザーは PSTN 会議番号を使用または<strong>[折り返し先]</strong>を使用してダイヤルインするのではなく、<strong>[Teams 会議に参加]</strong>ボタンをクリックして会議に参加することをお勧めします。 これにより、会議の数が多いことが PSTN ネットワークの混雑の原因となっているときに、音質を高められます。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>ユーザー エクスペリエンス

### <a name="join-a-meeting-by-using-phone-for-audio"></a>音声に電話を使って会議に参加する

[**参加]** をクリックして会議に参加し、[ビデオ **電話** オプションの選択] 画面で音声を再生し、[今すぐ参加] **をクリックします**。 ここから、ユーザーは会議の電話を受け、会議に参加したり、手動で会議にダイヤルインしたりすることができます。

![[オーディオ] オプション電話スクリーン ショット。](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**会議のTeamsを行う**

[音声 **に電話を使う** ] 画面で、ユーザーが自分の電話番号を入力し、[電話を受け取る] **をクリックします**。 会議はユーザーを呼び出し、会議に参加します。

![[音声に電話を使う] 画面の [通話] オプションのスクリーン ショット。](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**手動でダイヤルインする**

参加するもう 1 つの方法は、会議に直接ダイヤルインする方法です。 [音声 **に電話を使用** する] 画面で、[手動でダイヤルイン] をクリックして、会議にダイヤルインするために使用する電話番号の一覧を取得します。

![[手動でダイヤルイン] オプションのスクリーン ショット。](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>会議中に音声に問題が発生した場合に、通話を取り戻す

ユーザーが会議中にコンピューターを使用するときに音声の問題が発生した場合、ユーザーは電話を音声に簡単に使用する方法に切り替えます。 Teamsまたはデバイスの問題が発生した場合を検出し、[戻る] オプションを表示して、ユーザーが自分の電話を使用 **するリダイレクトを行** います。

次に示すのは、マイクが検出されない場合に表示されるメッセージと [Teams] オプションの例です。

![[戻る] オプションのスクリーン ショット。](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

ユーザーが [電話で **戻る]** をクリックすると、[音声に電話を使 **う] 画面が表示** されます。 ここから、電話番号を入力し、Teams通話を受け、会議に参加するか、手動で会議にダイヤルインできます。

## <a name="set-up-the-call-me-feature"></a>[通話] 機能を設定する

組織内のユーザーに対して [通話] 機能を有効にするには、次を構成する必要があります。

- 電話会議は、会議をスケジュールする組織内のユーザー (会議開催者) に対して有効になります。 詳細については、「Teams の[](set-up-audio-conferencing-in-teams.md)電話会議を設定する」および「Teams でユーザーの電話会議設定を管理する」[を参照してください](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

- 会議の開催者は、会議からダイヤルアウトできます。 詳細については、「ユーザーの電話[会議設定を](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)管理する」を参照Teams。

会議の開催者が会議からダイヤルアウトを有効にしない場合、[ビデオとオーディオのオプションの選択] 画面の **電話** 音声オプションは誰も使用できません。また、他のユーザーは会議に参加するための通話を受信できません。 ダイヤルアウトが有効になっているユーザーの場合、会議に参加すると、[参加者の表示] アイコンから他のユーザーが自分の番号をダイヤル **して参加** できます。
