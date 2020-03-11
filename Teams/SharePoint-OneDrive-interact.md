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
description: プライベート チャット ファイルの格納方法や、チーム、標準チャネル、ドキュメント ライブラリの関係など、Microsoft Teams との SharePoint Online および OneDrive for Business の連携について説明します。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 236b1d570d44395f3499c0a5fec3d3a415953e12
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834687"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Microsoft Teams との SharePoint Online と OneDrive for Business の連携

> [!Tip]
> Teams が Azure Active Directory (AAD)、Office 365 グループ、Exchange、SharePoint、および OneDrive for Business とどのようにやり取りするのかを学ぶために、次のセッションをご覧ください: [Microsoft Teamsの基礎](https://aka.ms/teams-foundations)。

Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各標準チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。

> [!NOTE]
> この記事は、標準チャネルにのみ適用されます。 プライベート チャネルのアーキテクチャは、標準チャネルとは異なります。 各プライベート チャネルには、親チームのサイトとは別個の SharePoint サイト コレクションがあります。 詳しくは、「[Microsoft Teams のプライベート チャネル](private-channels.md)」を参照してください。

プライベート チャット ファイルは送信者の OneDrive for Business フォルダーに格納され、権限はファイル共有プロセスの一環としてすべての参加者に付与されます。

ユーザーにSharePoint Onlineの有効なライセンスが割り当てられていない場合は、Office 365にOneDrive for Businessのストレージがありません。 ファイル共有は標準チャネル内で引き続き動作しますが、Office 365 に OneDrive for Business ストレージがないと、ユーザーはチャットでファイルを共有することができません。

SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。 

> [!NOTE]
> 現時点で Microsoft Teams の SharePoint オンプレミスとの統合はサポートされていません。

チーム、標準チャネル、ドキュメント ライブラリの関係の例を次に示します。

すべてのチームに対して SharePoint サイトが作成され、**[共有ドキュメント]** フォルダーがチーム用の既定のフォルダーとして作成されます。 **一般**チャネルを含め各標準チャネル (各チームの既定のチャネル) には、**共有ドキュメント**にフォルダーがあります。

![SharePoint Online の共有ドキュメント フォルダーの図。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> 既定の SharePoint サイトとドキュメント ライブラリを別のもので置き換えることは現時点ではできません。 この機能が必要であるという要望をいただきましたので、現在検討中です。 [Teams ロードマップ](https://aka.ms/teamsroadmap)または [Teams UserVoice](https://aka.ms/TeamsUserVoice) をチェックして、今後利用できるようになる機能について継続的に把握します。

> [!TIP]
> 既存のSharePointサイトページまたはSharePointドキュメントライブラリにリンクするチームにタブを追加するには：
> 1. タブの隣にある + 記号を選択します。
> 2. 既存のSharePointサイトページには**SharePoint**、あるいは既存のドキュメントライブラリには**Document Library**を選択します。
> 3. 適切なページまたはドキュメントライブラリを選択してください。

各ユーザーについては、他のユーザー (1 対 1 または 1 対多数 ) とのプライベート チャットで共有したすべてのファイルは OneDrive フォルダーの **Microsoft Teams Chat Files** に格納されます。このフォルダーには、指定したユーザーのみにアクセスを制限する権限が自動的に設定されます。

![Microsoft Teams Chat Files という名前が付けられた OneDrive フォルダーの図](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>チャネル ファイル タブ

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

Teams の **[ファイル]** タブは、SharePoint ドキュメント ビューによく似ています。 **[ファイル]** タブでは、次の操作を実行できます。

- **新規**ファイル メニューで追加オプションを確認する。
- ファイルをローカル ドライブに同期する。
- **[すべてのドキュメント]** メニューで **[リスト]** ビューを **[コンパクト リスト]**、**[タイル]** ビューに切り替える。
- 注意が必要なファイル、またはマルウェアのあるファイルを特定する。
- ファイルが読み取り専用かどうか、チェックアウト済みかどうかをすぐに確認する。
- ファイルをチェックインおよびチェックアウトする。
- ファイルのピン留め、ピン留め解除、並べ替え順序の変更を行う。
- メタデータが必要なファイルを特定する。
- 豊富なフィルター オプションの中から選択する。
- 列見出しに基づいてファイルをグループ化する。
- 列の設定 (左または右へ移動、非表示) と列の幅を変更する。

## <a name="default-link-type-setting"></a>既定のリンクの種類の設定

SharePoint と OneDrive には、ファイル用に作成されたリンクについて既定のリンクの種類を指定するための管理者設定があります。 Teams では、SharePoint と OneDrive の管理者による設定を再利用して、同じアプローチを採用します。 このアプローチについてさらに詳しくは、「[ユーザーが共有のリンクを取得するときの既定のリンクの種類を変更する](https://docs.microsoft.com/sharepoint/change-default-sharing-link)」で説明されています。 

## <a name="more-information"></a>詳細情報

SharePointがTeams とどのように連携するかの詳細については、[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)を参照してください。

Teams でのゲストのエクスペリエンス詳細については、[What the guest experience is like](guest-experience.md)を参照してください。

