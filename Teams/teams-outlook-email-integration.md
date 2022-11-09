---
title: アクション可能なアクティビティメールを管理する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams 会話のアクション可能なアクティビティ 電子メールを有効または無効にする方法について説明します
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43435c436685c53e0ad077887a9fe9d991cf2d61
ms.sourcegitcommit: f5480d0ca34b3160980a4b46b5afa34271293a26
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2022
ms.locfileid: "68899691"
---
# <a name="manage-actionable-activity-emails"></a>アクション可能なアクティビティメールを管理する

アクション可能なアクティビティメールは既定で有効になっており、組織内のユーザーに Microsoft Teams での会話が見逃されたことを通知します。

不在着信アクティビティの電子メールには、不在着信メッセージの後に送信されたメッセージなど、会話に対する最新の応答が表示されます。 この機能を使用すると、ユーザーは [返信] を選択して Outlook から直接 **返信** できます。

## <a name="disable-actionability-in-missed-activity-emails"></a>見逃したアクティビティメールのアクション可能性を無効にする

この機能は既定で有効に設定されていますが、次のコマンドを実行することで、組織全体のアクティビティ 電子メールのアクション可能性をオフにすることができます。

```Powershell
Set-OrganizationConfig -SmtpActionableMessagesEnabled $false
```

機能が無効になると、[ **返信** ] オプションが **Teams の [返信] に** 置き換えられ、見逃したアクティビティメールはアクション可能と見なされなくなります。 ユーザーは Outlook から直接応答できなくなり、Teams で会話を続けるよう指示されます。

> [!NOTE]
> この機能は、Outlook for Mac または一部の古いバージョンの Outlook for Windows ではサポートされていません。 詳細については、「[Outlook および Office 365 グループの操作可能なメッセージ](/outlook/actionable-messages/)」を参照してください。

## <a name="related-topics"></a>関連項目

[Outlook から見逃したアクティビティメールに返信します](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)。

[Outlook および Office 365 グループのアクション可能なメッセージ](/outlook/actionable-messages/)。
