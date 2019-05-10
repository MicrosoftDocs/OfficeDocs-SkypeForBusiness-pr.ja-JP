---
title: Microsoft Teams との SharePoint Online と OneDrive for Business の連携
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: プライベート チャット ファイルの格納方法、チーム、チャネル、ドキュメント ライブラリの関係など、Microsoft Teams との SharePoint Online および OneDrive for Business の連携について説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f790a01050811ee46526fe37a4d6c14f107491b5
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827741"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Microsoft Teams との SharePoint Online と OneDrive for Business の連携

> [!Tip]
> TeamsがAzure Active Directory（AAD）、Office 365グループ、Exchange、SharePoint、およびOneDrive for Businessとどのようにやり取りするのかを学ぶために、次のセッションをご覧ください: [Microsoft Teams の基礎](https://aka.ms/teams-foundations)

Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。

プライベート チャット ファイルは送信者の OneDrive for Business フォルダーに格納され、権限はファイル共有プロセスの一環としてすべての参加者に付与されます。

ユーザーにSharePoint Onlineの有効なライセンスが割り当てられていない場合は、Office 365にOneDrive for Businessのストレージがありません。 ファイル共有は引き続きチャンネルで機能しますが、Office 365のOneDrive for Businessストレージがないと、ユーザーはチャットでファイルを共有することはできません。

SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。 

> [!NOTE]
> この時点でマイクロソフトのチームは、SharePoint の設置型との統合がサポートされていません。

チーム、チャネル、ドキュメント ライブラリの関係の例を次に示します。

各チームには SharePoint サイトが作成されます。**共有ドキュメント** フォルダーは、そのチーム用に作成される既定のフォルダーです。各チャネル (各チームの既定のチャネルである**全般**チャネルを含む) には**共有ドキュメント**内にフォルダーが作成されます。

![Microsoft Teams のチームとそのチャネルに対応する SharePoint Online の共有ドキュメント フォルダーを示す図。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> 既定の SharePoint サイトとドキュメント ライブラリを別のもので置き換えることは現時点ではできません。 この機能が必要であるという要望をいただきましたので、現在検討中です。 [Teams ロードマップ](https://aka.ms/teamsroadmap)または [Teams UserVoice](https://aka.ms/TeamsUserVoice) をチェックして、今後利用できるようになる機能について継続的に把握します。

> [!TIP]
> 既存のSharePointサイトページまたはSharePointドキュメントライブラリにリンクするチームにタブを追加するには：
> 1. タブの隣にある + 記号を選択します。
> 2. 既存のSharePointサイトページには**SharePoint**、あるいは既存のドキュメントライブラリには**Document Library**を選択します。
> 3. 適切なページまたはドキュメントライブラリを選択してください。

各ユーザーについては、他のユーザー (1 対 1 または 1 対多数 ) とのプライベート チャットで共有したすべてのファイルは OneDrive フォルダーの **Microsoft Teams Chat Files** に格納されます。このフォルダーには、指定したユーザーのみにアクセスを制限する権限が自動的に設定されます。

![各ユーザーのチャットに対応する、Microsoft Teams Chat Files という名前が付けられた OneDrive フォルダーの図。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>チャネルの [ファイル] タブ

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

チームで、[**ファイル**] タブには、SharePoint のドキュメントのビューがよく似ています。 [**ファイル**] タブで、ユーザーは次のタスクを実行できます。

- **新規**の [ファイル] メニューの [追加のオプションを参照してください。
- ローカル ドライブにファイルを同期します。
- 上**のすべてのドキュメント**] メニューの [**リスト**] ビューの**最適化] ボックスの一覧**にビューに切り替えます**タイル**。
- 注意が必要、またはマルウェアのファイルを識別します。
- ファイルが読み取り専用か、またはチェックされたのかどうかをすぐに確認をします。
- チェック アウトし、ファイルをチェックインします。
- 固定し、固定を解除すると、ファイルの並べ替え順序を変更します。
- メタデータを必要があるファイルを識別します。
- 多数のフィルター オプションを選択します。
- 列見出しに基づいてファイルをグループ化。
- (移動左側または右側、非表示の列の設定と列の幅を変更します。

## <a name="default-link-type-setting"></a>既定のリンクの種類の設定

SharePoint および OneDrive ファイルに作成されるリンクの既定のリンクの種類を指定するため、管理者の設定があります。 チームは、管理者が SharePoint と OneDrive の設定の設定を再利用することによってその同じアプローチを採用しています。 この方法の詳細については、[リンクの種類では、ユーザーが共有へのリンクを取得するときに既定値を変更](https://docs.microsoft.com/sharepoint/change-default-sharing-link)することで説明します。 

## <a name="more-information"></a>詳細情報

SharePointがTeams とどのように連携するかの詳細については、[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)を参照してください。

Teams でのゲストのエクスペリエンス詳細については、[What the guest experience is like](guest-experience.md)を参照してください。

