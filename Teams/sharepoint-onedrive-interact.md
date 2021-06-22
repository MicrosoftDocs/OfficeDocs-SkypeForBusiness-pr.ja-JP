---
title: Microsoft Teams との SharePoint と OneDrive の連携
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: Teams を使用した SharePoint と OneDrive の相互作用、プライベート チャット ファイル ストレージ とチームとの相互作用、標準チャネルとドキュメント ライブラリ。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 21abc840ddc740d7d842767c6c864d8ff5b598dd
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855956"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a>Microsoft Teams との SharePoint と OneDrive の連携

> [!Tip]
> Teams が Azure Active Directory (AAD)、Microsoft 365 グループ、Exchange、SharePoint、および OneDrive とどのようにやり取りするのかを学ぶために、次のセッションをご覧ください: [Microsoft Teams の基礎](https://aka.ms/teams-foundations)。

Microsoft Teams の各チームには、SharePoint のチーム サイトがあります。チームの各標準チャネルには、既定のチーム サイトのドキュメント ライブラリ内のフォルダーが用意されています。 各[プライベート チャネル](private-channels.md)には、独自の分離した SharePoint サイトがあります。

会話内で共有されているファイルはドキュメント ライブラリに自動的に追加され、SharePoint で設定されているアクセス許可とファイルのセキュリティ オプションは、Teams 内に自動的に反映されます。 SharePoint でサイト アドレスを変更した場合の影響の詳細については、「[サイト アドレスを変更する](/sharepoint/change-site-address)」を参照してください。

プライベート チャット ファイルは送信者の OneDrive フォルダーに格納され、権限はファイル共有プロセスの一環としてすべての参加者に付与されます。

ユーザーに SharePoint のライセンスが割り当てられていない場合は、Microsoft 365 に OneDrive のストレージがありません。 ファイル共有は標準チャネル内で動作しますが、Microsoft 365 に OneDrive ストレージがないと、ユーザーはチャットでファイルを共有することができません。

SharePoint ドキュメント ライブラリと OneDrive にファイルを格納することで、組織レベルで構成されるすべてのコンプライアンス ルールが順守されます。 

> [!NOTE]
> SharePoint Server との統合は、Teams ではサポートされていません。

チーム、標準チャネル、ドキュメント ライブラリの関係の例を次に示します。

すべてのチームに対して SharePoint サイトが作成され、**[共有ドキュメント]** フォルダーがチーム用の既定のフォルダーとして作成されます。 **一般** チャネルを含め各標準チャネル (各チームの既定のチャネル) には、**共有ドキュメント** にフォルダーがあります。

![SharePoint の共有ドキュメント フォルダーの図。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

既定の SharePoint サイトやドキュメント ライブラリを別のものに置き換えることはできません。

各ユーザーについては、他のユーザー (1 対 1 または 1 対多数 ) とのプライベート チャットで共有したすべてのファイルは OneDrive フォルダーの **Microsoft Teams Chat Files** に格納されます。このフォルダーには、指定したユーザーのみにアクセスを制限する権限が自動的に設定されます。

![Microsoft Teams Chat Files という名前が付けられた OneDrive フォルダーの図](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

パブリック チームの場合、SharePoint チーム サイトには 「外部ユーザー以外のすべてのユーザー」のアクセスが設定されている点に注意してください。 チームのメンバーではないユーザーの場合、パブリック チームは Teams に表示されません。 ただし、SharePoint チーム サイトの URL を使用して SharePoint チーム サイト上のコンテンツにアクセスすることはできます。 

## <a name="channel-files-tab"></a>チャネル ファイル タブ

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

ユーザーがファイルを共有したときに既定で表示される共有リンクの種類は、SharePoint 管理センターで設定されます。 詳細については、「[ユーザーが共有のリンクを取得するときの既定のリンクの種類を変更する](/sharepoint/change-default-sharing-link)」を参照してください。

## <a name="related-topics"></a>関連トピック

[SharePoint とTeams: 共同作業の効率化](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。

[ゲストのエクスペリエンスについて](guest-experience.md)