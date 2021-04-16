---
title: Microsoft Teams との SharePoint Online と OneDrive for Business の連携
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: Teams を使用した SharePoint Online と OneDrive for Business の相互作用、プライベート チャット ファイル ストレージ とチームとの相互作用、標準チャネルとドキュメント ライブラリ。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b69b156e5cea0ff63925e91f5e3c077c794b3425
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117035"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Microsoft Teams との SharePoint Online と OneDrive for Business の連携

> [!Tip]
> Teams が Azure Active Directory (AAD)、Microsoft 365 グループ、Exchange、SharePoint、および OneDrive for Business とどのようにやり取りするのかを学ぶために、次のセッションをご覧ください: [Microsoft Teams の基礎](https://aka.ms/teams-foundations)。

Microsoft Teams の各チームには、SharePoint Online のチーム サイトがあります。チームの各標準チャネルには、既定のチーム サイトのドキュメント ライブラリ内のフォルダーが用意されています。 会話内で共有されているファイルはドキュメント ライブラリに自動的に追加され、SharePoint で設定されているアクセス許可とファイルのセキュリティ オプションは、Teams 内に自動的に反映されます。 SharePoint でサイト アドレスを変更した場合の影響の詳細については、「[サイト アドレスを変更する](/sharepoint/change-site-address)」を参照してください。

> [!NOTE]
> この記事は、標準チャネルにのみ適用されます。 プライベート チャネルのアーキテクチャは、標準チャネルとは異なります。 各プライベート チャネルには、親チームのサイトとは別個の SharePoint サイト コレクションがあります。 詳しくは、「[Microsoft Teams のプライベート チャネル](private-channels.md)」を参照してください。

プライベート チャット ファイルは送信者の OneDrive for Business フォルダーに格納され、権限はファイル共有プロセスの一環としてすべての参加者に付与されます。

ユーザーに SharePoint Online の有効なライセンスが割り当てられていない場合は、Microsoft 365 やOffice 365 に OneDrive for Business のストレージがありません。 ファイル共有は標準チャネル内で引き続き動作しますが、Microsoft 365 または Office 365 に OneDrive for Business ストレージがないと、ユーザーはチャットでファイルを共有することができません。

SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。 

> [!NOTE]
> 現時点で Microsoft Teams の SharePoint オンプレミスとの統合はサポートされていません。

チーム、標準チャネル、ドキュメント ライブラリの関係の例を次に示します。

すべてのチームに対して SharePoint サイトが作成され、**[共有ドキュメント]** フォルダーがチーム用の既定のフォルダーとして作成されます。 **一般** チャネルを含め各標準チャネル (各チームの既定のチャネル) には、**共有ドキュメント** にフォルダーがあります。

![SharePoint Online の共有ドキュメント フォルダーの図。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> 既定の SharePoint サイトとドキュメント ライブラリを別のもので置き換えることは現時点ではできません。 この機能が必要であるという要望をいただきましたので、現在検討中です。 [Teams ロードマップ](https://aka.ms/teamsroadmap)または [Teams UserVoice](https://aka.ms/TeamsUserVoice) をチェックして、今後利用できるようになる機能について継続的に把握します。

> [!TIP]
> 既存のSharePointサイトページまたはSharePointドキュメントライブラリにリンクするチームにタブを追加するには：
> 1. タブの隣にある + 記号を選択します。
> 2. 既存のSharePointサイトページには **SharePoint**、あるいは既存のドキュメントライブラリには **Document Library** を選択します。
> 3. 適切なページまたはドキュメントライブラリを選択してください。

各ユーザーについては、他のユーザー (1 対 1 または 1 対多数 ) とのプライベート チャットで共有したすべてのファイルは OneDrive フォルダーの **Microsoft Teams Chat Files** に格納されます。このフォルダーには、指定したユーザーのみにアクセスを制限する権限が自動的に設定されます。

![Microsoft Teams Chat Files という名前が付けられた OneDrive フォルダーの図](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

パブリック チームの場合、SharePoint チーム サイトには 「外部ユーザー以外のすべてのユーザー」のアクセスが設定されている点に注意してください。 チームのメンバーではないユーザーの場合、パブリック チームは Teams に表示されません。 ただし、SharePoint チーム サイトの URL を使用して SharePoint チーム サイト上のコンテンツにアクセスすることはできます。 

## <a name="channel-files-tab"></a>チャネル ファイル タブ

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

Teams の **[ファイル]** タブは、SharePoint ドキュメント ビューによく似ています。 **[ファイル]** タブでは、次の操作を実行できます。

- **新規** ファイル メニューで追加オプションを確認する。
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

SharePoint と OneDrive には、ファイル用に作成されたリンクについて既定のリンクの種類を指定するための管理者設定があります。 Teams では、SharePoint と OneDrive の管理者による設定を再利用して、同じアプローチを採用します。 このアプローチについてさらに詳しくは、「[ユーザーが共有のリンクを取得するときの既定のリンクの種類を変更する](/sharepoint/change-default-sharing-link)」で説明されています。 

## <a name="more-information"></a>詳細情報

SharePointがTeams とどのように連携するかの詳細については、[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)を参照してください。

Teams でのゲストのエクスペリエンス詳細については、[What the guest experience is like](guest-experience.md)を参照してください。