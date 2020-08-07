---
title: Microsoft Teams との SharePoint Online と OneDrive for Business の連携
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & Teams での OneDrive for Business の操作プライベートチャットファイルストレージ & チーム、標準チャネル、& ドキュメントライブラリ間の相互作用。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: af9981b1f3cd95d80a72a9e4fa536835d662382d
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581088"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Microsoft Teams との SharePoint Online と OneDrive for Business の連携

> [!Tip]
> チームと Azure Active Directory (AAD)、Microsoft 365 グループ、Exchange、SharePoint、および OneDrive for Business がどのように連携するかについては、次のセッションをご覧ください。 [Microsoft Teams の基礎](https://aka.ms/teams-foundations)

Microsoft Teams の各チームには SharePoint Online のチームサイトがあり、チーム内の各標準チャネルは既定のチームサイトのドキュメントライブラリ内のフォルダーを取得します。会話内で共有されているファイルは、ドキュメントライブラリに自動的に追加されます。また、SharePoint で設定された権限とファイルセキュリティオプションは、自動的に Teams 内に反映されます。SharePoint でサイトのアドレスを変更した場合の影響を確認するには、「[サイトアドレスを変更](https://docs.microsoft.com/sharepoint/change-site-address)する」を参照してください。

> [!NOTE]
> この記事は、標準チャネルにのみ適用されます。 プライベート チャネルのアーキテクチャは、標準チャネルとは異なります。 各プライベート チャネルには、親チームのサイトとは別個の SharePoint サイト コレクションがあります。 詳しくは、「[Microsoft Teams のプライベート チャネル](private-channels.md)」を参照してください。

プライベートチャットファイルは、送信者の OneDrive for Business フォルダーに保存され、ファイル共有プロセスの一環としてすべての参加者に対してアクセス許可が自動的に付与されます。

ユーザーが SharePoint Online ライセンスを割り当てて有効にしていない場合、Microsoft 365 または Office 365 の OneDrive for Business ストレージはありません。 ファイルの共有は、引き続き標準チャネルでの作業を続けますが、Microsoft 365 または Office 365 では、OneDrive for Business ストレージを使わずに、チャットでファイルを共有することはできません。

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

パブリックチームの場合、SharePoint チームサイトには、"外部ユーザー以外のすべてのユーザー" アクセスがプロビジョニングされていることに注意してください。 パブリックチームは、チームのメンバーでないユーザーのために Teams に表示されません。 ただし、sharepoint チームサイトの URL を使用して SharePoint チームサイトのコンテンツにアクセスすることができます。 

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

