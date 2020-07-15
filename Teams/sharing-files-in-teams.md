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
description: Microsoft Teams でのファイル共有のエクスペリエンスについて説明します。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138351"
---
# <a name="sharing-files-in-microsoft-teams"></a>Microsoft Teams でのファイル共有

Microsoft Teams では、ユーザーは組織内外の他の Teams ユーザーとコンテンツを共有できます。 Teams での共有は、SharePoint と OneDrive で構成されている設定に基づいているため、SharePoint と OneDrive のどちらを設定しても、Teams での共有が制御されます。

## <a name="overview"></a>概要

ユーザーは、アクセス権を持つチームやサイトから、または自分のコンピューターからファイルを共有できます。 ファイルを共有するには、次の操作を行います。

- チャネルで、[**添付**] (クリップアイコン) をクリックし、[**最近使用**したファイル] を選択し、[**チームとチャネル**]、[ **OneDrive**] を参照するか、[**マイコンピューターからアップロード**] をクリックして、共有するファイルを選びます。 <br> 
    ![チャネルからのファイルの共有を示すスクリーンショット](media/share-files-channel.png)
- チャットで、[**添付**] (クリップアイコン) をクリック**するか、** [**マイコンピューターからアップロード**] をクリックして、共有するファイルを選択します。 <br>
    ![チャットからのファイルの共有を示すスクリーンショット](media/share-files-chat.png)
- 作成ボックスの共有リンクをコピーして貼り付けます。<br>
    ![作成ボックスのファイルプレビューを示すスクリーンショット](media/share-files-link.png)

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a>ファイル共有のエクスペリエンスについて知っておくべきこと

### <a name="permissions-of-shared-files-and-sharing-links"></a>共有ファイルと共有リンクの権限

OneDrive またはチームおよびチャネルでファイルを参照してファイルを共有すると、すべての受信者に、[組織レベルで設定された既定のアクセス許可](https://docs.microsoft.com/sharepoint/change-default-sharing-link)が与えられます。

ユーザーが共有リンクをコピーして貼り付けると、その共有リンクに設定されているアクセス許可が有効になり、SharePoint URL はファイル名に短縮されます。 つまり、Teams はファイル名だけを使ってファイルにリンクします。

ユーザーが Teams 内からファイルを共有する場合、Microsoft 365 全体での場合と同様に、ファイルにアクセスできるユーザーを設定することができます。 ユーザーは、組織内のユーザー、既存のアクセス権を持つユーザー、または特定のユーザーにアクセス権を付与することができます (ユーザーを1:1 チャット、グループチャット、またはチャネルに含めることができます)。  ファイルが共有されている場合、ファイルのプレビューは、 **[オンラインで開く**]、[**ダウンロード**]、[**コピー**] などのすべてのファイル操作と共に、メッセージで使用できます。 既定では、ファイルは Teams で開きます。 場合によっては、ユーザーがメッセージを送信したときに、共有リンクがファイルプレビューに変換されないことがあります。 ファイルプレビューはシステムによって生成されますが、このシナリオでは、ファイル名のみに共有リンクを短縮することはできません。

ユーザーがチャットまたはチャネルでファイルを共有すると、一部またはすべての受信者にファイルを表示する権限がないかどうかが通知されます。 ファイルを共有する前に、ファイルのアクセス許可を変更することができます。これで、メッセージに表示されるファイルプレビューの横にある矢印をクリックします。

![受信者が権限を持っていない場合の通知のスクリーンショット](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a>Teams で共有リンクをコピーする

ユーザーは、Microsoft 365 と同じように、SharePoint 共有リンクをコピーし、共有権限を変更することができます。 組織内のユーザー、既存のアクセス権を持つユーザー、または特定のユーザーにアクセス権を付与することができます。 リンクの既定のアクセス許可は、SharePoint のサイトレベルの権限を上書きしない限り、組織レベルで設定された既定の権限セットと同じです。

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a>OneDrive と SharePoint の共有を構成する

OneDrive と SharePoint でのファイルの共有について詳しくは、「共有を構成する方法」と「共有を有効または無効にする方法」をご覧ください。

- [外部共有の概要](https://docs.microsoft.com/sharepoint/external-sharing-overview)-ユーザーが共有している内容や他のユーザーが共有しているときの動作について説明します。

- [共有設定を管理](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)する-グローバルと sharepoint 管理者が Sharepoint と OneDrive の組織レベルの共有設定を変更する方法について説明します。

- [サイトの外部共有を有効または無効](https://docs.microsoft.com/sharepoint/change-external-sharing-site)にする–グローバルと SharePoint 管理者がサイトの外部共有を有効または無効にする方法について説明します。

- [サイトの既定のリンクの種類を変更](https://docs.microsoft.com/sharepoint/change-default-sharing-link)する-既定のリンクの種類を設定して、より制限されるようにする方法について説明します。

## <a name="more-information"></a>詳細情報

- [Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)

- [SharePoint とチーム: 共同作業を効率化する](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [OneDrive のファイルとフォルダーを共有する](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [SharePoint のファイルまたはフォルダーを共有する](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
