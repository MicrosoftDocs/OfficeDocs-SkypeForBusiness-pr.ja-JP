---
title: ユーザー用に通話機能を設定する
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: ユーザーがオーディオ用にコンピューターを使用している可能性がある場合に、ユーザーが電話でオーディオ部分に参加できるように、Teams の [折り返し] 機能を設定する方法について説明します。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f1ffee416b1d5674e831fda4c5bb15a89c510f4
ms.sourcegitcommit: 1ddd29e3839e50387efb4ec7b9d2154991bb2642
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35432140"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>ユーザー用に通話機能を設定する

Microsoft Teams の [**折り返し**] 機能を使用すると、ユーザーは電話で会議のオーディオ部分に参加することができます。 これは、オーディオ用のコンピューターを使うことができない場合に便利です。 ユーザーは、会議のオーディオ部分を、携帯電話または陸上線と、会議の他の参加者&mdash;が自分の画面を共有したり、コンピューターでビデオ&mdash;を再生したりする場合に、会議のコンテンツ部分を取得します。

## <a name="the-user-experience"></a>ユーザーエクスペリエンス

会議に参加するには、[**参加**] をクリックし、[**オーディオとビデオの設定を選択して**ください] 画面で [電話の**オーディオ**] をクリックします。 ここでは、ユーザーが会議通話を使用して会議に参加したり、手動で会議にダイヤルインしたりすることができます。

![[電話] オーディオオプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**チームに会議通話を許可する**

[**オーディオ用に電話を使う**] 画面で、ユーザーは電話番号を入力し、[**折り返し**先] をクリックします。 会議はユーザーを呼び出し、会議に参加します。

![[オーディオ用電話を使う] 画面の [折り返し先] オプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**手動でダイヤルする**

もう1つの方法は、会議に直接ダイヤルインすることです。 [**オーディオ用に電話を使う**] 画面で、[**手動でダイヤル**する] をクリックして、会議にダイヤルインするために使用する電話番号の一覧を表示します。

![[手動でダイヤルする] オプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

## <a name="set-up-the-call-me-feature"></a>[折り返し先] 機能を設定する

組織内のユーザーに対して [折り返して呼び出す] 機能を有効にするには、次の設定を行う必要があります。

- 会議をスケジュールする組織内のユーザー (会議の開催者) では、電話会議が有効になっています。 詳細については、「 [teams の電話会議をセットアップ](set-up-audio-conferencing-in-teams.md)する」および「 [teams でユーザーの電話会議の設定を管理](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)する」を参照してください。

- ユーザーは会議からダイヤルアウトできます。 詳細については、「 [Teams でユーザーの電話会議の設定を管理](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)する」を参照してください。

ユーザーが会議からのダイヤルアウトを有効にして**** いない場合、[折り返し先] オプションは利用できません。ユーザーは会議に参加するための電話を受けません。 代わりに、電話で電話の会議に手動でダイヤルインするために使うことができる電話番号のリストが、[**オーディオの使用電話**] 画面に表示されます。

