---
title: Microsoft Teams でインライン メッセージの翻訳を使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
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
ms.openlocfilehash: 466160616adea80a2fcb6a3bfd035ca397d73754
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754427"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Microsoft Teams でインライン メッセージの翻訳を使用する 
=================================================

インライン メッセージの翻訳は、新しい Microsoft Teams の機能で、ユーザーが Teams のメッセージを、Office 365 のパーソナル言語設定で指定した[言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)に自動的に翻訳できるようになります。

インライン メッセージの翻訳は、所属する組織に対しては既定でロール アウトされています。 チーム クライアント内でこの機能を使用するユーザーを許可する場合は、この設定を有効にする必要があります。

> [!NOTE]
>このロールアウトは、Office 365 の政府コミュニティ クラウドと Office 365 のドイツの環境での Office 365 サブスクリプションから除外されます。

## <a name="enable-by-using-powershell"></a>PowerShell を使用して有効にします。

インライン メッセージの翻訳機能をオンするには、メッセージング ポリシーを使用しています。

1. [セット CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)コマンドレットを使用してポリシーを有効にします。
2. ポリシーは、適用には数分をかかります。 ユーザーがサインアウトして、チームにもう一度サインインする必要があります。

## <a name="enable-by-using-the-microsoft-teams-admin-center"></a>マイクロソフトのチーム管理センターを使用して有効にします。

**マイクロソフト チームの管理センター**で**メッセージング ポリシー**を選択して、左側のバーから、新しいポリシーを作成または既存のポリシーを編集し、**メッセージを変換するユーザーを許可する**] オプションを**オン**に設定。

> [!NOTE]
>翻訳はサービスによって実行し、対応レコード内でキャプチャされたコンテンツに影響をクライアントに配信します。 翻訳機能の詳細についてを参照してください[Microsoft Translator は何ですか?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)。