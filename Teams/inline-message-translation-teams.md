---
title: インライン メッセージの翻訳を有効にする
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
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams 管理センターまたは PowerShell を使用して Microsoft Teams でインライン翻訳を有効にする方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c9e34c5e539d32b25259098973e9bfe6795ad7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120628"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Microsoft Teams でインライン メッセージの翻訳をオフにする
=================================================

インライン メッセージの翻訳は、ユーザーが Teams メッセージを個人の[](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)言語設定で指定された言語に翻訳できる Microsoft Teams の機能です。

インライン メッセージの翻訳は、組織に対して既定で展開されます。 ユーザーが Teams クライアント内でこの機能を使用できる場合は、変更を加える必要があります。

> [!NOTE]
>このロールアウトは、Office 365 Government Community Cloud および Office 365 Germany の環境での Office 365 サブスクリプションから除外されています。

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>PowerShell を使用してインライン メッセージの翻訳をオフにする

メッセージング ポリシーを使用して、インライン メッセージの翻訳をオフにできます。

[Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)コマンドレットを使用してポリシーをオフにします。 ポリシーが適用されるには数分間かかります。 ユーザーは、サインアウトして再び Teams にサインインする必要があります。

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Microsoft Teams 管理センターを使用してインライン メッセージの翻訳をオフにする

Microsoft **Teams** 管理センターで、左側のナビゲーションから [**メッセージング** ポリシー] を選択し、新しいポリシーを作成するか、既存のポリシーを編集し、[メッセージの翻訳] オプションを [オフ] に設定 **します**。

> [!NOTE]
> サービスは翻訳を行い、コンプライアンス レコードに取り込むコンテンツに影響を与え、クライアントに配信します。 翻訳の詳細については [、「Microsoft Translator とは」を参照してください。](/azure/cognitive-services/translator/translator-info-overview)