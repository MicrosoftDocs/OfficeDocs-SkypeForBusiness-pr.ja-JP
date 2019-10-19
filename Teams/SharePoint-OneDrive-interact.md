---
title: Microsoft Teams との SharePoint Online と OneDrive for Business の連携
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: プライベート チャット ファイルの格納方法、チーム、チャネル、ドキュメント ライブラリの関係など、Microsoft Teams との SharePoint Online および OneDrive for Business の連携について説明します。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af1d12eda58dc481ba28bf96ff4ecbfeab8ed5f0
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "37567121"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Microsoft Teams との SharePoint Online と OneDrive for Business の連携

> [!Tip]
> TeamsがAzure Active Directory（AAD）、Office 365グループ、Exchange、SharePoint、およびOneDrive for Businessとどのようにやり取りするのかを学ぶために、次のセッションをご覧ください: [Microsoft Teams の基礎](https://aka.ms/teams-foundations)

Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。

プライベート チャット ファイルは送信者の OneDrive for Business フォルダーに格納され、権限はファイル共有プロセスの一環としてすべての参加者に付与されます。

ユーザーにSharePoint Onlineの有効なライセンスが割り当てられていない場合は、Office 365にOneDrive for Businessのストレージがありません。 ファイル共有は引き続きチャンネルで機能しますが、Office 365のOneDrive for Businessストレージがないと、ユーザーはチャットでファイルを共有することはできません。

SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。 

> [!NOTE]
> 現時点では、オンプレミスの SharePoint との統合はサポートされていません。

チーム、チャネル、ドキュメント ライブラリの関係の例を次に示します。

各チームには SharePoint サイトが作成されます。**共有ドキュメント** フォルダーは、そのチーム用に作成される既定のフォルダーです。各チャネル (各チームの既定のチャネルである**全般**チャネルを含む) には**共有ドキュメント**内にフォルダーが作成されます。

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

