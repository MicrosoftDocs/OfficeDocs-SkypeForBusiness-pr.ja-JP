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
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016838"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Microsoft Teams でインライン メッセージの翻訳を使用する 
=================================================

インライン メッセージの翻訳は、新しい Microsoft Teams の機能で、ユーザーが Teams のメッセージを、Office 365 のパーソナル言語設定で指定した[言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)に自動的に翻訳できるようになります。

インライン メッセージ変換されていました、組織の既定の設定をします。 チーム クライアント内でこの機能を使用するユーザーを許可する場合を有効にしてこの設定で、PowerShell を使用します。 現時点では、このオプションは、マイクロソフトのチームとのビジネス管理センターでは、Skype では使用できませんが、すぐにします。

> [!NOTE]
>このロールアウトは、Office 365 Government Community Cloud および Office 365 Germany の環境での Office 365 サブスクリプションから除外されています。 

## <a name="enable-by-using-powershell"></a>PowerShell を使用して有効にする

メッセージング ポリシーを使用することで、インライン メッセージの翻訳機能をオンにすることができます。 

1. [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) コマンドレットを使用して、ポリシーをオンにします。
2. ポリシーは、適用には数分をかかります。 ユーザーがサインアウトして、チームにもう一度サインインする必要があります。

## <a name="enable-by-using-the-teams-admin-center"></a>Teams 管理センターを使用して有効にする

Teams 管理センターを使用してインライン メッセージの翻訳機能をオンにするオプションは、近日中に利用できるようになります。

> [!NOTE]
>翻訳とは、厳密には、クライアント側とは、コンテンツへの影響はキャプチャされません対応レコードで。 翻訳機能の詳細についてを参照してください[Microsoft Translator は何ですか?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)。