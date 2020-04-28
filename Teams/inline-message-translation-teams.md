---
title: インラインメッセージの翻訳を有効にする
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
description: Microsoft Teams 管理センターまたは PowerShell を使用して、Microsoft Teams でインライン翻訳を有効にする方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fabdbde6f8307694457d4861d67c6ed2eb22ac1
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905809"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a>Microsoft Teams でインラインメッセージの翻訳を有効にする 
=================================================

インラインメッセージの翻訳は、ユーザーが Office 365 の個人の言語設定で指定された[言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)にチームのメッセージを翻訳できるようにする、Microsoft Teams の新機能です。

インライン メッセージの翻訳は、所属する組織に対しては既定でロール アウトされています。 Teams クライアント内でユーザーがこの機能を使用することができるようにする場合、この設定をオンにする必要があります。

> [!NOTE]
>このロールアウトは、Office 365 Government Community Cloud および Office 365 Germany の環境での Office 365 サブスクリプションから除外されています。

## <a name="use-powershell-to-turn-on-inline-message-translation"></a>PowerShell を使用してインラインメッセージの翻訳を有効にする

メッセージポリシーを使って、インラインメッセージの翻訳を有効にすることができます。

[Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) コマンドレットを使用して、ポリシーをオンにします。 ポリシーが適用されるには数分間かかります。 ユーザーは、サインアウトして再び Teams にサインインする必要があります。

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a>Microsoft Teams 管理センターを使用して、インラインメッセージの翻訳を有効にする

**Microsoft Teams 管理センター**で、左のナビゲーションから [**メッセージポリシー** ] を選び、新しいポリシーを作成するか、既存のポリシーを編集して、[**メッセージの翻訳を許可**する] オプションを **[オン**] に設定します。

> [!NOTE]
> サービスは翻訳を行ってクライアントに配信し、コンプライアンスレコードでキャプチャされたコンテンツには影響しません。 翻訳の詳細については、「[Microsoft Translator とは](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)」をご覧ください。