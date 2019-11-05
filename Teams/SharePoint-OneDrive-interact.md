---
title: Microsoft Teams との SharePoint Online と OneDrive for Business の連携
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online と OneDrive for Business が、プライベートチャットファイルの保存方法、チーム、標準チャネル、ドキュメントライブラリ間の関係など、Microsoft Teams とどのように連携するかについて説明します。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b18cf1f97d0798df5cac4881672c0756cc56616
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968248"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Microsoft Teams との SharePoint Online と OneDrive for Business の連携

> [!Tip]
> TeamsがAzure Active Directory（AAD）、Office 365グループ、Exchange、SharePoint、およびOneDrive for Businessとどのようにやり取りするのかを学ぶために、次のセッションをご覧ください: [Microsoft Teams の基礎](https://aka.ms/teams-foundations)

Microsoft Teams の各チームには SharePoint Online のチームサイトがあり、チーム内の各標準チャネルは既定のチームサイトのドキュメントライブラリ内のフォルダーを取得します。会話内で共有されているファイルは、ドキュメントライブラリに自動的に追加されます。また、SharePoint で設定された権限とファイルセキュリティオプションは、自動的に Teams 内に反映されます。

> [!NOTE]
> この記事は、標準チャネルにのみ適用されます。 プライベートチャネルのアーキテクチャは、標準チャネルとは異なります。 各プライベートチャネルには、親チームサイトとは別の固有の SharePoint サイトコレクションがあります。 詳細については、「 [Microsoft Teams のプライベートチャネル](private-channels.md)」を参照してください。

プライベート チャット ファイルは送信者の OneDrive for Business フォルダーに格納され、権限はファイル共有プロセスの一環としてすべての参加者に付与されます。

ユーザーにSharePoint Onlineの有効なライセンスが割り当てられていない場合は、Office 365にOneDrive for Businessのストレージがありません。 ファイルの共有は、引き続き標準チャネルでの作業を続けますが、Office 365 では、OneDrive for Business の記憶域なしでチャットでファイルを共有することはできません。

SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。 

> [!NOTE]
> 現時点では、オンプレミスの SharePoint との統合はサポートされていません。

次の例は、チーム、標準チャネル、ドキュメントライブラリ間の関係を示しています。

すべてのチームに対して、SharePoint サイトが作成され、[**共有ドキュメント**] フォルダーがチーム用に作成された既定のフォルダーになります。 **一般的な**チャネル (各チームの既定のチャネル) を含む各標準チャネルには、**共有ドキュメント**内のフォルダーがあります。

![SharePoint Online の共有ドキュメントフォルダーの図](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> 既定の SharePoint サイトとドキュメント ライブラリを別のもので置き換えることは現時点ではできません。 この機能が必要であるという要望をいただきましたので、現在検討中です。 [Teams ロードマップ](https://aka.ms/teamsroadmap)または [Teams UserVoice](https://aka.ms/TeamsUserVoice) をチェックして、今後利用できるようになる機能について継続的に把握します。

> [!TIP]
> 既存のSharePointサイトページまたはSharePointドキュメントライブラリにリンクするチームにタブを追加するには：
> 1. タブの隣にある + 記号を選択します。
> 2. 既存のSharePointサイトページには**SharePoint**、あるいは既存のドキュメントライブラリには**Document Library**を選択します。
> 3. 適切なページまたはドキュメントライブラリを選択してください。

各ユーザーについては、他のユーザー (1 対 1 または 1 対多数 ) とのプライベート チャットで共有したすべてのファイルは OneDrive フォルダーの **Microsoft Teams Chat Files** に格納されます。このフォルダーには、指定したユーザーのみにアクセスを制限する権限が自動的に設定されます。

![Microsoft Teams のチャットファイルという名前の OneDrive フォルダーの図](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>[チャネルファイル] タブ

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

Teams の [**ファイル**] タブは、SharePoint ドキュメントビューとよく似ています。 [**ファイル**] タブでは、ユーザーは次のことができます。

- [**新しい**ファイル] メニューの [その他のオプション] を参照してください。
- ファイルをローカルドライブに同期します。
- [**すべてのドキュメント**] メニューで、**リスト**ビューから [**コンパクト] リスト**を [**タイル**] ビューに切り替えます。
- 注意が必要なファイルまたはマルウェアがあるファイルを特定します。
- ファイルが読み取り専用であるかチェックアウトされているかをすぐに確認します。
- ファイルのチェックアウトとチェックインを行います。
- ファイルの並べ替え、ピン留めの解除、並べ替え順序の変更を行う。
- メタデータが必要なファイルを特定する
- さらに多くのフィルターオプションを選択します。
- 列見出しに基づいてファイルをグループ化します。
- 列の設定を変更する (左または右に移動、非表示)、列幅を変更します。

## <a name="default-link-type-setting"></a>既定のリンクの種類の設定

SharePoint と OneDrive には、ファイルに対して作成されるリンクの既定のリンクの種類を指定する管理者設定があります。 チームでは、管理者が SharePoint と OneDrive 用に設定した設定を再利用することにより、同じ方法を採用しています。 この方法について詳しくは[、「ユーザーが共有のリンクを取得するときの既定のリンクの種類を変更する](https://docs.microsoft.com/sharepoint/change-default-sharing-link)」をご覧ください。 

## <a name="more-information"></a>詳細情報

SharePointがTeams とどのように連携するかの詳細については、[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)を参照してください。

Teams でのゲストのエクスペリエンス詳細については、[What the guest experience is like](guest-experience.md)を参照してください。

