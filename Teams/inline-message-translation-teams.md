---
title: Microsoft Teams でインライン メッセージの翻訳を使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でインラインの翻訳を使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9097e7421bb65b1a9ce0900df097080a6cfc2023
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296397"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Microsoft Teams でインライン メッセージの翻訳を使用する 
=================================================

インライン メッセージの翻訳は、新しい Microsoft Teams の機能で、ユーザーが Teams のメッセージを、Office 365 のパーソナル言語設定で指定した[言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)に自動的に翻訳できるようになります。

インライン メッセージの翻訳は、所属する組織に対しては既定でロール アウトされています。 Teams クライアント内でユーザーがこの機能を使用することができるようにする場合、PowerShell を使用してこの設定をオンにする必要があります。 現在、このオプションは Microsoft Teams と Skype for Business の管理センターでは利用できませんが、近日中に利用できるようになります。

> [!NOTE]
>このロールアウトは、Office 365 Government Community Cloud および Office 365 Germany の環境での Office 365 サブスクリプションから除外されています。 

## <a name="enable-by-using-powershell"></a>PowerShell を使用して有効にする

メッセージング ポリシーを使用することで、インライン メッセージの翻訳機能をオンにすることができます。 

1. [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) コマンドレットを使用して、ポリシーをオンにします。
2. ポリシーが適用されるには数分間かかります。 ユーザーは、サインアウトして再び Teams にサインインする必要がある可能性があります。

## <a name="enable-by-using-the-teams-admin-center"></a>Teams 管理センターを使用して有効にする

Teams 管理センターを使用してインライン メッセージの翻訳機能をオンにするオプションは、近日中に利用できるようになります。

> [!NOTE]
>翻訳は完全にクライアント側によるものであり、コンプライアンスの記録で取得されたコンテンツには影響しません。 翻訳の詳細については、「[Microsoft Translator とは](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)」をご覧ください。