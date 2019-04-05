---
title: Microsoft Teams でインライン メッセージの翻訳を使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でインラインの翻訳を使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58e6fb04dd015e939125b75d604fe9692a32c0e2
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459909"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Microsoft Teams でインライン メッセージの翻訳を使用する 
=================================================

インライン メッセージの翻訳は、新しい Microsoft Teams の機能で、ユーザーが Teams のメッセージを、Office 365 のパーソナル言語設定で指定した[言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)に自動的に翻訳できるようになります。

インライン メッセージの翻訳は、所属する組織に対しては既定でロール アウトされています。 Teams クライアント内でユーザーがこの機能を使用することができるようにする場合、この設定をオンにする必要があります。

> [!NOTE]
>このロールアウトは、Office 365 Government Community Cloud および Office 365 Germany の環境での Office 365 サブスクリプションから除外されています。

## <a name="enable-by-using-powershell"></a>PowerShell を使用して有効にする

メッセージング ポリシーを使用することで、インライン メッセージの翻訳機能をオンにできます。

1. [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) コマンドレットを使用して、ポリシーをオンにします。
2. ポリシーが適用されるには数分間かかります。 ユーザーは、サインアウトして再び Teams にサインインする必要があります。

## <a name="enable-by-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターを使用して有効にする

**Microsoft Teams 管理センター**で、左側のバーから [**メッセージング ポリシー**] を選択し、新しいポリシーを作成するか、既存のポリシーを編集して、[**ユーザーにメッセージの翻訳を許可する**] オプションを**オン**に設定します。

> [!NOTE]
>サービスにより翻訳が実行され、コンプライアンス レコードでキャプチャされたコンテンツに影響のないクライアントに配信されます。 翻訳の詳細については、「[Microsoft Translator とは](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)」をご覧ください。