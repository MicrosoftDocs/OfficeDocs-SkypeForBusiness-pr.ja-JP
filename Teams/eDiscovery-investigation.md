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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233493"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Microsoft Teams のコンテンツに対して電子情報開示の調査を行う
============================

大企業は、多くの場合、電子的に保存されている情報 (ESI) の申請を要求する高ペナルティ法的手続きにさらされています。

すべての Teams 1:1 またはグループチャットは、それぞれのユーザーのメールボックスにジャーナリングされ、すべてのチャネルメッセージは、チームを表すグループメールボックスにジャーナリングされます。 アップロードされたファイルについては、SharePoint Online と OneDrive for business の電子情報開示機能の下に記載されています。

1.  Microsoft Teams のコンテンツで電子情報開示の調査を実施するには、[この](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)リンクの手順1を確認してください。

2.  Microsoft Teams のデータは、Excel eDiscovery のエクスポート出力で IM または会話として表示され、をマウントすることができます。[Outlook の PST からエクスポート後のメッセージを表示します。

    をマウントします。[PST] チームの場合は、すべてのスレッドが [会話履歴] の下にあるチームチャットフォルダーに保存されていることに注意してください。 メッセージのタイトルは、チームとチャネルに揃えて配置されます。 以下の画像を確認すると、製造仕様チームのプロジェクト7チャネルを送信先しているボブからのメッセージが表示されます。

    ![Outlook のユーザーのメールボックス内のチームチャットフォルダーのスクリーンショット](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  ユーザーのメールボックスのプライベート チャットは、会話履歴のチーム チャット フォルダーにも格納されています。

## <a name="ediscovery-of-guest-to-guest-chats"></a>ゲスト間のチャットの電子情報開示

メールボックスがなくても、ゲスト間のチャット (ホームテナントのユーザーがいない1xN のチャット) にはインデックスが作成されず、結果として電子情報開示に含まれません。 ゲスト間チャットの電子情報開示を容易にするために、クラウドベースのメールボックス (またはファントムのメールボックス) を作成して、1xN データを保存します。 チームチャットデータがクラウドベースのメールボックスに保存された後、電子情報開示およびコンプライアンスコンテンツ検索のインデックスが作成されます。

次の図は、メールボックスがないゲスト間チャットでの電子情報開示の動作を示しています。

![ゲスト間-チャット-メールボックスなし](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
