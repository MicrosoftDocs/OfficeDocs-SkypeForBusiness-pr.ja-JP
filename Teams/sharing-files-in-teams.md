---
title: Microsoft Teams でのファイル共有
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Microsoft Teams のファイル共有機能について説明します。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138351"
---
# <a name="sharing-files-in-microsoft-teams"></a>Microsoft Teams でのファイル共有

Microsoft Teams では、組織内外の他の Teamsユーザーとコンテンツを共有できます。 Teamsでの共有は、SharePoint と OneDrive に構成されている設定に基づいているため、SharePoint および OneDrive 用の設定が、チームの共有も制御します。

## <a name="overview"></a>概要

ユーザーは、OneDrive、アクセス権が与えられているチームやサイトおよびコンピューターからのファイルを共有することができます。 ファイルを共有するには、次の操作を行います。

- チャネルで、[**添付**] (ペーパークリップ アイコン)、[**最近使用した**]、[**Teams とチャネルを参照**] をクリックして、[**OneDrive**] または、[**マイコンピューターから アップロード**] の順にクリックして、共有するファイルを選びます。 <br> 
    ![ファイルをチャネルから共有しているスクリーンショット](media/share-files-channel.png)
- チャットで、[**添付** ] (ペーパークリップのアイコン) をクリックして、[**OneDrive**] または [**マイコンピューターから アップロード**] を選択して、共有するファイルを選択します。 <br>
    ![チャットからのファイルの共有を示したスクリーンショット](media/share-files-chat.png)
- 作成ボックスに共有リンクをコピーして貼り付けます。<br>
    ![[作成] ボックスにファイルのプレビューを表示しているスクリーンショット](media/share-files-link.png)

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a>ファイル共有機能について知っておくべきこと

### <a name="permissions-of-shared-files-and-sharing-links"></a>共有ファイルと共有リンクのアクセス許可

ユーザーが OneDrive またはチームとチャネルでファイルを参照してファイルを共有すると、すべての受信者に「[組織レベルに設定されている既定のアクセス許可](https://docs.microsoft.com/sharepoint/change-default-sharing-link)」に準拠してアクセス権が与えられます。

ユーザーが共有リンクをコピーして貼り付けたときに、その共有リンクに設定されているアクセス許可が優先され、SharePoint の URL が短くなりファイル名になります。 つまり、Teams は、ファイル名だけを使用してファイルにリンクします。

ユーザーが Teams 内からファイルを共有する場合、Microsoft 365 の場合と同様に、ファイルにアクセスできるユーザーを設定できます。 既存のアクセス権を持つユーザー、または特定のユーザー (1:1 チャット、グループチャット、チャネルのユーザーを含む) など、組織内のどのユーザーにもアクセス権を与えることができます。  ファイルが共有されている場合はメッセージでファイルのプレビューが表示されます。これには、 **オンラインでオープン**、**ダウンロード**、**リンクをコピー** といった、あらゆるアクションも同時に表示されます。 既定では、ファイルは [Teams] で開きます。 ユーザーがメッセージを送信する時に、共有リンクがファイルプレビューに変換されていないことがあります。 ファイルのプレビューはシステムによって作成されますが、このシナリオでは、共有リンクをファイル名のみに縮めてしまうことはありません。

ユーザーがチャットやチャネルでファイルを共有すると、一部またはすべての受信者がファイルを表示する権限を持っているか、いないかが通知されます。 ファイルを共有する前に、メッセージに表示されるファイルプレビューの横にある矢印をクリックすると、ファイルのアクセス許可を変更できます。

![受信者にアクセス許可がない場合の通知のスクリーンショット](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a>共有リンクを Teams にコピーする

Microsoft 365 の場合と同様に、ユーザーは SharePoint 共有リンクをコピーすることも、共有アクセス許可を変更することもできます。 既存のアクセス権を持つユーザー、または特定のユーザーなど、組織内のすべてのユーザーにアクセス権を与えることができます。 リンクの既定のアクセス許可は、SharePoint サイト レベルの権限を優先しない限り、組織レベルで設定された既定のアクセス許可と同じです。

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a>OneDrive と SharePoint の共有を構成する

共有を構成する方法、共有を有効または無効にする方法など、OneDrive と SharePoint でファイルを共有する方法の詳細については、以下を参照してください。

- [外部共有の概要](https://docs.microsoft.com/sharepoint/external-sharing-overview) - 共有する内容と相手に応じて、ユーザーが共有したときの動作について説明します。

- [共有設定の管理](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - グローバルおよび SharePoint 管理者が、SharePoint および OneDrive の組織レベルの共有設定を変更する方法について説明します。

- [サイトの外部共有を有効または無効にする](https://docs.microsoft.com/sharepoint/change-external-sharing-site) –グローバルおよび SharePoint 管理者がサイトの外部共有を有効または無効にする方法について説明します。

- [サイトの既定のリンクの種類を変更する](https://docs.microsoft.com/sharepoint/change-default-sharing-link) -制約を厳しくするように既定のリンクの種類を設定する方法について説明します。

## <a name="more-information"></a>詳細情報

- [Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)

- [SharePoint とTeams: 共同作業の効率化](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [OneDrive のファイルとフォルダーの共有](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [SharePoint のファイルまたはフォルダを共有する](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
