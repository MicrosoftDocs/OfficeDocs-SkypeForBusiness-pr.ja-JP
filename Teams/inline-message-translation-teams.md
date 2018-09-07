---
title: インライン メッセージの変換を使用して、マイクロソフトのチームで
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: salilda
localization_priority: Priority
search.appverid: MET150
description: マイクロソフトのチームでのインライン変換を使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb7876d015fb736785fdaab99b1ed71b8e05b9dc
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855822"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>インライン メッセージの変換を使用して、マイクロソフトのチームで 
=================================================

インライン メッセージの変換は、自動的にチームのメッセージを Office 365 の場合は、その個人の言語設定で指定された[言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)に翻訳することができる新しいマイクロソフトのチーム機能です。

インライン メッセージ変換されていました、組織の既定の設定をします。 チーム クライアント内でこの機能を使用するユーザーを許可する場合を有効にしてこの設定で、PowerShell を使用します。 現時点では、このオプションは、マイクロソフトのチームとのビジネス管理センターでは、Skype では使用できませんが、すぐにします。

> [!NOTE]
>このロールアウトは、Office 365 の政府コミュニティ クラウドと Office 365 のドイツの環境での Office 365 サブスクリプションから除外されます。 

## <a name="enable-by-using-powershell"></a>PowerShell を使用して有効にします。

インライン メッセージの翻訳機能をオンするには、メッセージング ポリシーを使用しています。 

1. [セット CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)コマンドレットを使用してポリシーを有効にします。
2. ポリシーは、適用には数分をかかります。 ユーザーがサインアウトして、チームにもう一度サインインする必要があります。

## <a name="enable-by-using-the-teams-admin-center"></a>チーム管理センターを使用して有効にします。

チーム管理センターを使用して、インライン メッセージの翻訳機能を有効にするオプションがもうすぐ完成です。

> [!NOTE]
>翻訳とは、厳密には、クライアント側とは、コンテンツへの影響はキャプチャされません対応レコードで。 翻訳機能の詳細についてを参照してください[Microsoft Translator は何ですか?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)。