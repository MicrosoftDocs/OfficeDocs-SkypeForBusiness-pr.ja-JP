---
title: ユーザーの [電話する] 機能をセットアップする
author: CarolynRowe
ms.author: crowe
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Teams で通話機能を設定して、コンピューターをオーディオに使用できない場合にユーザーが電話で音声部分に参加できるようにする方法について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a144e6a751f44ff520ee0317dbbcb390f30abbfd
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794535"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>ユーザーの [電話する] 機能をセットアップする

Microsoft Teams では、 **通話** 機能を使用すると、ユーザーは電話で会議のオーディオ部分に参加できます。 これは、オーディオにコンピューターを使用できない場合に便利です。 ユーザーは、携帯電話や陸路を介して会議のオーディオ部分を取得し、別の会議参加者が画面を共有したり、コンピューターを介してビデオ&mdash;を再生したりする場合など、会議&mdash;のコンテンツ部分を取得します。

> [!IMPORTANT]
> 
> (新型コロナウイルス感染症の発生で) 会議の数が多い間は、ユーザーは PSTN 会議番号を使用または<strong>[折り返し先]</strong>を使用してダイヤルインするのではなく、<strong>[Teams 会議に参加]</strong>ボタンをクリックして会議に参加することをお勧めします。 これにより、会議の数が多いことが PSTN ネットワークの混雑の原因となっているときに、音質を高められます。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>ユーザー エクスペリエンス

### <a name="join-a-meeting-by-using-phone-for-audio"></a>音声に電話を使用して会議に参加する

[**参加**] をクリックして会議に参加し、[**ビデオとオーディオのオプションの選択**] 画面で **[電話オーディオ**] をクリックし、[**今すぐ参加**] をクリックします。 ここから、ユーザーは会議の呼び出しを行い、会議に参加したり、会議に手動でダイヤルインしたりできます。

![Phone オーディオ オプションのスクリーン ショット。](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Teams 会議の呼び出しを許可する**

**[音声に電話を使用** する] 画面で、ユーザーが自分の電話番号を入力し、[**通話**] をクリックします。 会議はユーザーを呼び出し、会議に参加します。

![[電話をオーディオに使用] 画面の [通話] オプションのスクリーン ショット。](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**手動でダイヤルインする**

参加するもう 1 つの方法は、会議に直接ダイヤルインすることです。 [ **通話に電話を使用** する] 画面 **で、[ダイヤルイン] を手動で** クリックして、会議へのダイヤルインに使用する電話番号の一覧を取得します。

![[手動でダイヤルする] オプションのスクリーン ショット。](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>会議中に音声に問題が発生した場合にコールバックを受け取る

ユーザーが会議中にコンピューターを使用しているときにオーディオの問題が発生した場合、ユーザーは簡単に自分の電話をオーディオに使用するように切り替えることができます。 Teams は、オーディオまたはデバイスの問題がいつ発生したかを検出し、 **コールバック** オプションを表示してユーザーに電話を使用するようリダイレクトします。

Teams がマイクを検出しない場合に表示されるメッセージと **コールバック** オプションの例を次に示します。

![[コールバック] オプションのスクリーン ショット。](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

ユーザーが [ **コールバック**] をクリックすると、[電話を使用して **オーディオ** ] 画面が表示されます。 ここから、電話番号を入力し、Teams 会議の通話を行い、会議に参加したり、会議に手動でダイヤルインしたりできます。

## <a name="set-up-the-call-me-feature"></a>通話機能を設定する

組織内のユーザーに対して通話機能を有効にするには、次を構成する必要があります。

- 電話会議は、会議をスケジュールする組織内のユーザー (会議の開催者) に対して有効になります。 詳細については、「[Teams の電話会議のセットアップと Teams の](set-up-audio-conferencing-in-teams.md)[ユーザーの電話会議設定の管理」を参照してください](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

- 会議の開催者は、会議からダイヤルアウトできます。 詳細については、「 [Teams でユーザーの電話会議設定を管理する](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)」を参照してください。

会議の開催者が会議からのダイヤルアウトを有効にしていない場合、[**ビデオとオーディオ** オプションの選択] 画面の **[電話オーディオ**] オプションはだれも利用できず、他のユーザーは会議に参加するための通話を受け取ることはできません。 ダイヤルアウトが有効になっているユーザーの場合、会議に参加すると、[参加者の表示] アイコンから自分の番号をダイヤルする他 **のユーザーに** 参加できます。
