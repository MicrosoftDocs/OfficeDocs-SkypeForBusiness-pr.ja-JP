---
title: Microsoft Teams でチャネルのモデレーションを設定および管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: チームメンバーをチャネルモデレーターとして追加する方法など、Microsoft Teams でモデレーション用にチャネルをセットアップする方法について説明します。
ms.openlocfilehash: 62a184334e337b1e5f30e2373223db1fe52ea477
ms.sourcegitcommit: 67282b5f2f1aac3e675c4a485f4846deba15deb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "35841455"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>Microsoft Teams でチャネルのモデレーションを設定および管理する

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft Teams では、チーム所有者はチャネルのモデレーションを有効にして、誰が新しい投稿を開始し、そのチャネルで投稿に返信できるかを制御できます。

チーム所有者は、チームメンバーをモデレーターとして追加することもできます。 チャネルの調停を最大限にサポートするために、チーム所有者はチャネルレベルで分野の専門知識を持っていない可能性があります。 特定のチームメンバーがチャネルをモデレートすることを許可することにより、チャネル内でコンテンツとコンテキストを管理する責任が、チーム所有者とチャネルモデレーターの間で共有されます。 たとえば、チーム所有者はモデレーターとしてビジネスオーナーまたはコンテンツ所有者を追加できます。これにより、そのチャネルでの情報共有を制御できます。

## <a name="what-can-a-channel-moderator-do"></a>チャネルモデレーターは何を行うことができますか?

チャネルモデレーターは次のことができます。

- チャネルで新しい投稿を開始します。 チャネルのモデレーションを有効にすると、モデレーターのみがそのチャネルで新しい投稿を開始できます。
- チームメンバーをモデレーターとしてチャネルに追加したり、削除したりします。 既定では、チーム所有者はチャネルモデレーターであり、削除することはできないことに注意してください。
- チームメンバーが既存のチャネルメッセージに返信できるかどうか、また、ボットとコネクタがチャネルメッセージを送信できるかどうかを制御します。

## <a name="scenarios"></a>シナリオ

組織で Teams でチャネルモデレートを使用する方法の例を次に示します。

### <a name="use-a-channel-as-an-announcement-channel"></a>チャネルをアナウンスメントチャネルとして使用する

マーケティングチームは、特定のチャネルを使用して、主要なプロジェクトのお知らせと成果物を共有します。 チームメンバーがコンテンツをチャネルに投稿したときに、他のチャネルにより適切に属していることがあります。 チーム所有者は、チャネル内での情報共有をお知らせのみに制限し、チームメンバーがそのチャネルを使用して重要な情報を把握できるようにする必要があります。

このシナリオでは、チーム所有者がモデレーターとしてマーケティングリーダーを追加して、チャネルにお知らせを投稿し、チームメンバーがそのチャネルのメッセージに返信することができないようにします。

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>チームの教育機関向けのクラスディスカッションにチャネルを使用する

教育機関向けの Teams では、科学教師はチャネルを使用して、特定の教室のトピックについての焦点を絞ったディスカッションで学生を協力したいと思います。

このシナリオでは、教師は教職員の助手にチャネルをモデレートすることを許可しています。 次に、教職員のアシスタントは、学生とのディスカッションを開始して運転するための新しい投稿を作成できます。

## <a name="manage-channel-moderation"></a>チャネルのモデレーションを管理する

Teams でチャネルに移動し、[**その他のオプション...** ] をクリックします。 > **チャンネルを管理**する。 ここでは、モデレートを有効または無効にしたり、チームメンバーをモデレーターとして追加したり、ユーザー設定を行うことができます。

![manage-channel-moderation-in-teams-preferences](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>チャネルのモデレーションを有効または無効にする

既定では、モデレーションはオフであり、新しい投稿をチームメンバーのみに制限するか、ゲストを含むすべてのユーザーに新しい投稿を開始することを許可することができます。

チャネルのモデレーションを有効にするには、[**チャネルのモデレーション**] で [**オン**] をクリックします。 チャネルのモデレーションがオンになっている場合、モデレーターのみが新しい投稿を開始できます。 

### <a name="add-or-remove-channel-moderators"></a>チャネルモデレーターを追加または削除する

[**モデレーターはだれですか**] の下で、[**管理**] をクリックし、チームメンバーをモデレーターとして追加または削除します。 チーム所有者とモデレーターは、他のモデレーターを追加および削除できます。  

### <a name="set-team-member-permissions"></a>チームメンバーの権限を設定する

[**チームメンバーの権限**] で、許可するアクティビティの横にあるチェックボックスをオンにします。

## <a name="related-topics"></a>関連トピック

- [Teams でのチームとチャネルの概要](teams-channels-overview.md)