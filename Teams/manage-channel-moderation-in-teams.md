---
title: チャネルのモデレーションを設定および管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: チーム メンバーをチャネルのモデレーターとして追加する方法を含む、Microsoft Teams でモデレート用にチャネルを設定する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6cdf6988afb9afbd91c2bfd19ed516c8e8fdf702
ms.sourcegitcommit: 379bfaf6b0584c1ac93341af605f93ab932a442b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240617"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>Microsoft Teams でチャネルのモデレーションを設定および管理する

Microsoft Teams では、チーム所有者は、標準チャネルのモデレーションを有効にして、誰が新しい投稿を開始し、そのチャネルで投稿に返信できるかを制御できます。

チーム所有者は、チーム メンバーをモデレーターとして追加することもできます。 チーム所有者が、チャネルのモデレーションを最大限にサポートするためのチャネル レベルにおける領域の専門知識を持っていない場合もあります。 特定のチーム メンバーがチャネルをモデレートすることを許可することにより、チャネル内のコンテンツとコンテキストを管理する責任を、チーム所有者とチャネル モデレーターで共有できます。 たとえば、チーム所有者はモデレーターとしてビジネス オーナーまたはコンテンツ所有者を追加できます。これにより、対象チャネルで共有する情報を制御できます。

> [!NOTE]
> 現時点では、チャネルの調停機能は標準のチャネルで利用できます。 プライベートチャネルでは使用できません。

## <a name="what-can-a-channel-moderator-do"></a>チャネル モデレーターが行えること

チャネル モデレーターは次のことができます。

- チャネルで新しい投稿を開始します。 チャネルでモデレーションを有効にすると、モデレーターのみがそのチャネルで新しい投稿を開始できます。
- チーム メンバーをモデレーターとしてチャネルに追加したり、削除したりします。 既定では、チーム所有者はチャネル モデレーターであり、チーム所有者を削除することはできません。
- チーム メンバーが既存のチャネル メッセージに返信できるかどうか、また、ボットとコネクタがチャネル メッセージを送信できるかどうかを制御します。

## <a name="scenarios"></a>シナリオ

組織が Teams でチャネルのモデレーションを使用する方法の例を次に示します。

### <a name="use-a-channel-as-an-announcement-channel"></a>チャネルをお知らせチャネルとして使用する

マーケティング チームは、特定のチャネルを使用して、主要なプロジェクトのお知らせと成果物を共有します。 チーム メンバーがチャネルに投稿したコンテンツが、他のチャネルに属するほうがより適切であることがあります。 チーム所有者は、このチャネルで共有する情報をお知らせのみに制限し、チーム メンバーがそのチャネルを使用して重要な情報をいつでも把握できるようにすることができます。

このシナリオでは、チーム所有者がモデレーターとしてマーケティング リーダーを追加して、チャネルにお知らせを投稿し、チーム メンバーがそのチャネルのメッセージに返信できないようにすることができます。

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>Teams for Education におけるクラス ディスカッション用にチャネルを使用する

Teams for Education では、科学の教師がチャネルを使用して、特定の授業トピックに的を絞ったディスカッションに生徒を参加させることができます。

このシナリオでは、教師は、補助教員がチャネルをモデレートすることを許可します。 次に、補助教員は、新しい投稿を作成し、学生とのディスカッションを開始して促進できます。

## <a name="manage-channel-moderation"></a>チャネルのモデレーションを管理する

Teams でチャネルに移動し、**[その他のオプション...]** > **[チャネルを管理]** とクリックします。 ここでは、モデレーションを有効または無効にしたり、チーム メンバーをモデレーターとして追加したり、設定を行ったりすることができます。

チャネルのモデレーションは、チャネルごとの設定です。 チャネルのモデレーションのテナント レベルの設定はありません。 テナント レベルのチャネルのモデレーション設定を追加する場合は、[Teams UserVoice](https://microsoftteams.uservoice.com/) で要求します。

![manage-channel-moderation-in-teams-preferences.png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>チャンルのモデレーションを有効または無効にする

既定では、モデレーションは無効になっています。これは、通常のチャネル設定がチーム所有者とチーム メンバーに適用されることを意味します。 たとえば、新しい投稿をチーム メンバーのみに制限したり、ゲストを含むすべてのユーザーに新しい投稿の開始を許可したりできます。

チャネルのモデレーションを有効にするには、**[チャネルのモデレーション]** の **[有効 (On)]** をクリックします。 チャネルのモデレーションが有効になっている場合、モデレーターのみが新しい投稿を開始できます。 

### <a name="add-or-remove-channel-moderators"></a>チャネル モデレーターを追加または削除する

**[モデレーター一覧]** で **[管理]** をクリックし、チーム メンバーをモデレーターとして追加または削除します。 チーム所有者とモデレーターは、他のモデレーターを追加および削除できます。  

### <a name="set-team-member-permissions"></a>チーム メンバーのアクセス許可を設定する

**[チーム メンバーのアクセス許可]** で、許可するアクティビティの隣にあるチェックボックスを選択します。

## <a name="related-topics"></a>関連項目

- [Teams でのチームとチャネルの概要](teams-channels-overview.md)
