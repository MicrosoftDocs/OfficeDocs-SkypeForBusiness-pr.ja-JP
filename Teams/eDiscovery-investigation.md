---
title: Microsoft Teams のコンテンツに対して電子情報開示の調査を行う
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 訴訟手続きのためにすべての電子保持情報を提出する必要がある場合など、電子情報開示を実施するために必要な手続きについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54ccb21e33c6acc1747023fc7c3eb174040d5746
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461805"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Microsoft Teams のコンテンツに対して電子情報開示の調査を行う
============================

大企業は、多くの場合、提出書類のすべて電子的に格納されている情報 (ESI) を必要とするペナルティの法的手続きに公開されます。

すべての 1 対 1 のチームまたはグループのチャットは、各ユーザーのメールボックスに、履歴として保存されたと、すべてのチャネル メッセージは、チームを表すグループのメールボックスを履歴として保存されました。アップロードされたファイルは、SharePoint Online およびビジネスのための OneDrive の電子的証拠開示機能で説明します。

1.  マイクロソフトのチームのコンテンツを電子的証拠開示調査を実施するには、[この](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)リンクでは、手順 1 を参照してください。

2.  IM とマイクロソフトのチームのデータが表示されます、出力をエクスポートする Excel の電子的証拠開示での会話やマウントすることができます、します。これらのメッセージを表示するのには Outlook の PST は、エクスポートを転記します。

    マウントするとします。チーム、チーム チャットで会話の履歴フォルダー内のすべての会話が保存されているメモの PST です。 メッセージのタイトルは、チームおよびチャネルに配置します。 下の画像を確認するには、製造仕様のチームのプロジェクトの 7 チャネル メッセージの数に Bob からのこのメッセージを表示できます。

    ![チーム チャット Outlook でユーザーのメールボックス フォルダーのスクリーン ショット](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  ユーザーのメールボックスのプライベート チャットは、会話履歴のチーム チャット フォルダーにも格納されています。

## <a name="ediscovery-of-guest-to-guest-chats"></a>ゲストからゲストのチャットについては、電子的証拠開示

ゲストからゲストへのチャット、メールボックスを持たない (1xN のチャットは、ユーザーがホームのテナントがない) がないインデックスを作成して、結果として、電子的証拠開示では含まれない。 ゲストからゲストのチャットの電子的証拠開示をさせるために、1xN データを格納するクラウド ベースのメールボックス (またはメールボックスの幻) が作成されます。 チーム チャットのデータは、クラウド ベースのメールボックスに格納されている後、は、電子的証拠開示およびコンプライアンスのコンテンツの検索にインデックスされます。

次の図では、ゲストからゲストのチャット、メールボックスがない、電子的証拠開示のしくみを示しています。

![guest-to-guest-chats-with-no-mailbox](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
