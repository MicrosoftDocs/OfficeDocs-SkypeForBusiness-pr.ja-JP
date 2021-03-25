---
title: チームを作成するときの Microsoft 365 グループの計画
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Teams での Microsoft 365 グループの計画について説明します。たとえば、Teams でのグループと Teams の会話&、Teams がグループの名前付けポリシーを尊重する方法などです。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 1acde038bc2df64d7cf35828bf0b08273bf1f095
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108353"
---
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a>Microsoft Teams でチームを作成するときに Microsoft 365 グループを計画する
==========================================================

Microsoft 365 グループの使用を検討する場合、またはチームを作成する場合は、チームの使用目的、アクセス権を持つユーザー、チームが達成すると予想される結果について検討します。 ユーザーがコンテンツが細すぎる (チャネルが多すぎる) ほどオーバーランする可能性がある場合は、作成するチャネルの数に特に注意してください。

Microsoft 365 グループの計画と Microsoft Teams への影響 (または Microsoft Teams による) に関する議論が必要なシナリオは 2 つ考えられます。

-   最初に、お客様はグループに既存の投資を行う可能性があります。現在、パブリック グループとプライベート グループの両方がサポートされています。現在サポートされているメンバー数については [、Microsoft Teams](./limits-specifications-teams.md)の制限と仕様を参照してください。 前に説明したように、Microsoft 365 管理センターではなく、Teams クライアントを使用してチームへのユーザーのメンバーシップを管理する必要があります。 このシナリオを考えると、ユーザーが Microsoft 365 グループでスレッド化された会話に慣れる場合、グループの会話は本質的にメールであり、Teams チャネルのチャット メッセージとは異なっている点に気を付け価値があります。 この違いについてユーザーを教育し、より柔軟なチャット メッセージ形式を Teams で採用し、Outlook または OWA を使用してグループにメールを送信するよりも望ましいことを提案します。

-   次に、Microsoft 365 で定義されている既存のグループをお持ちではないお客様は、Microsoft 365 管理センター、Teams Web、またはデスクトップ クライアントを使用してグループを作成できます。 前述のように、Teams クライアントを使用して、Microsoft 365 グループの今後のすべてのメンバーシップを管理します。 チームのメンバーシップは Microsoft 365 グループのメンバーシップも定義していますので、この変更に備える必要があります。

## <a name="teams-respects-microsoft-365-groups-naming-policy-in-private-preview"></a>Teams は Microsoft 365 グループの名前付けポリシーを尊重します (プライベート プレビューで)

管理者によって設定された Microsoft 365 グループの名前付けポリシーは、ユーザーがチーム名を作成または編集するときに Teams に適用されます。 これには必須のプレフィックスやサフィックス、禁止された単語の除外などの事項が含まれます。

> [!NOTE]
> この機能はプライベート プレビューに含まれるので、このプレビューに参加していない場合、Teams は Microsoft 365 グループの名前付けポリシーにまだ準拠していません。

詳細については、Teams の [Microsoft 365 グループの名前付けポリシーを参照してください](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。

次の記事は、Microsoft 365 グループの準備と導入のコンテンツを見つけるのに役立ちます。

-   [Get more with groups in Outlook (Outlook でグループを活用する)](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [Microsoft 365 管理センターを使用して Microsoft 365 グループのメンバーを追加または削除する](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [削除したグループを復元する](/microsoft-365/admin/create-groups/restore-deleted-group)