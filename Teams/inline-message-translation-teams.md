---
title: インライン メッセージ翻訳を有効にする
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
description: 管理センターまたは PowerShell を使用して、Microsoft TeamsインラインMicrosoft Teamsを有効にする方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 719f97e72f099edb4d14c22ef9d5a3de0f787ea7411f42f1d777ea842bcc4e27
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339645"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a>メッセージのインライン翻訳をオフMicrosoft Teams

インライン メッセージ翻訳は、ユーザー Microsoft Teamsの言語設定で指定された言語にTeamsメッセージ[](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)を翻訳できる機能です。

インライン メッセージの翻訳は、組織に対して既定で展開されます。 クライアント内でユーザーにこの機能の使用を許可する場合は、変更を加えるTeams必要があります。

> [!NOTE]
>このロールアウトは、Office 365 Government Community Cloud および Office 365 Germany の環境での Office 365 サブスクリプションから除外されています。

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>PowerShell を使用してインライン メッセージ変換をオフにする

メッセージング ポリシーを使用して、インライン メッセージ変換をオフにできます。

[Set-CsTeamsMessagingPolicy コマンドレットを使用してポリシーをオフ](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)にします。 ポリシーが適用されるには数分間かかります。 ユーザーは、サインアウトして再び Teams にサインインする必要があります。

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>管理センター Microsoft Teamsを使用して、インライン メッセージの翻訳をオフにする

Microsoft Teams **管理** センター で、左側のナビゲーションから [**メッセージング** ポリシー] を選択し、新しいポリシーを作成するか、既存のポリシーを編集し、[メッセージの翻訳] オプションを [オフ] に設定 **します**。

> [!NOTE]
> サービスは翻訳を行い、コンプライアンス レコードにキャプチャされたコンテンツに影響を与え、クライアントに配信します。 翻訳の詳細については、「翻訳とは[」をMicrosoft 翻訳ツール。](/azure/cognitive-services/translator/translator-info-overview)