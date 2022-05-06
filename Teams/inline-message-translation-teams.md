---
title: インライン メッセージ変換を有効にする
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams管理センターまたは PowerShell を使用して、Microsoft Teamsでインライン翻訳を有効にする方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bfaa03ff8fa8654fca48fbd2bd31d8d6518e2de
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593081"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Microsoft Teamsでインライン メッセージ変換を無効にする

インライン メッセージ翻訳は、ユーザーが自分の言語設定で指定された[言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)にTeamsメッセージを翻訳できるようにするMicrosoft Teams機能です。

インライン メッセージ変換は、組織に対して既定でロールアウトされます。 ユーザーがTeams クライアント内でこの機能を使用できるようにする場合は、変更する必要はありません。

> [!NOTE]
>このロールアウトは、Office 365 Government Community Cloud および Office 365 Germany の環境での Office 365 サブスクリプションから除外されています。

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>PowerShell を使用してインライン メッセージ変換を無効にする

メッセージング ポリシーを使用して、インライン メッセージ変換を無効にすることができます。

[Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) コマンドレットを使用してポリシーをオフにします。 ポリシーが適用されるには数分間かかります。 ユーザーは、サインアウトして再び Teams にサインインする必要があります。

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Microsoft Teams管理センターを使用してインライン メッセージ変換を無効にする

**Microsoft Teams管理センター** で、左側のナビゲーションから **[メッセージング ポリシー**] を選択し、新しいポリシーを作成するか、既存のポリシーを編集して、[**メッセージの翻訳**] オプションを **[オフ]** に設定します。

> [!NOTE]
> サービスは翻訳を行い、コンプライアンス レコードにキャプチャされたコンテンツに影響を与えない状態でクライアントに配信します。 翻訳の詳細については、「Microsoft 翻訳ツールとは[」](/azure/cognitive-services/translator/translator-info-overview)を参照してください。