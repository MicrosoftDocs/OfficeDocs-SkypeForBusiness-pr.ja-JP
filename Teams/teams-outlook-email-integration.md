---
title: Teams と Outlook のメール統合
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: ユーザーが Outlook のメールと Teams のチャットやチャネルの会話の間で情報を共有できる機能など、Teams と Outlook のメール統合機能について学習します。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6e260148cfcdb45c516958bae03ecfadc1bbd64
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802397"
---
# <a name="teams-and-outlook-email-integration"></a>Teams と Outlook のメール統合

Microsoft Teams には、組織内のユーザーが Outlook のメールと Teams のチャットまたはチャネルの会話の間で情報を共有し、見逃した会話を簡単に確認できる機能が含まれています。 この記事では、これらの機能と適用される管理者コントロールの概要について説明します。

## <a name="share-to-outlook"></a>Outlook と共有する

**Outlook で共有すると** 、ユーザーは Teams から離れることなく、Teams の会話のコピーを Outlook のメールに共有できます。 この機能は、ユーザーが会話や状態の更新をチーム外のユーザーや組織のユーザーと共有する必要がある場合に便利です。 Teams で会話の一番上に移動し **、[ 3** のオプション] を選択し **、[Outlook** に共有] を選択します。  詳細については、「Teams から [Outlook に共有する」を参照してください](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)。

![Teams の [Outlook と共有] 機能を示すスクリーンショット](media/share-to-outlook.png)

この機能を使用するには、ユーザーに対して Outlook on the web を有効にしている必要があります。 Outlook on the web がオフになっている場合、ユーザーの Teams で **[Outlook** に共有] オプションは表示されません。 Outlook on the web を有効または無効にする方法の手順については、「メールボックスの Outlook on the web を有効または [無効にする」を参照してください](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)。

## <a name="actionable-activity-emails"></a>操作可能なアクティビティ のメール

ユーザーは、Teams の見逃した会話を検出するのに役立つ、操作可能な見逃したアクティビティ メールを自動的に取得します。 見逃したアクティビティのメールには、見逃したメッセージの後に送信されたメッセージなど、会話からの最新の返信が表示され、ユーザーは[返信] をクリックして Outlook 内から直接返信できます。 詳細については、「Outlook から見逃 [したアクティビティ メールに返信する」を参照してください](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)。 

> [!NOTE]
> この機能は、Outlook for Mac または一部の古いバージョンの Outlook for Windows ではサポートされていません。 詳細については、Outlook および [365 グループのアクション可能Officeを参照してください](https://docs.microsoft.com/outlook/actionable-messages/)。

![見逃したアクティビティのメールを示すスクリーンショット](media/missed-activity-email.png)

![見逃したアクティビティメールに返信する方法を示すスクリーンショット](media/missed-activity-email-reply.png)

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig)コマンドレットと **SmtpActionableMessagesEnabled** パラメーターを使用して、アクション可能なメールをオフにできます。 既定では **、SmtpActionableMessagesEnabled パラメーター** は true に設定 **されています**。 パラメーターを false に **設定すると** 、アクション可能なメール メッセージが 365 Officeされます。 Teams ユーザーの場合、Outlookで直接返信する返信オプションは、見逃したアクティビティ メールでは利用できません。 代わりに、見逃したアクティビティ メールには、ユーザーが Teams で返信する **[Teams** で返信] オプションが含まれます。
