---
title: データSharePoint操作OneDrive方法Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDriveと対話Teams。プライベート チャット ファイル ストレージ&、標準チャネル、およびドキュメント ライブラリ&操作できます。
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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855956"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a>データSharePoint操作OneDrive方法Microsoft Teams

> [!Tip]
> Azure Active Directory (A Microsoft 365 AD)、Azure Active Directory グループ、Exchange、Exchange、SharePoint、OneDrive: Microsoft Teams の基礎と対話する方法については、次のセッションをご[覧ください](https://aka.ms/teams-foundations)Microsoft Teams Teams

Microsoft Teams内の各チームは SharePoint にチーム サイトを持ち、チーム内の各標準チャネルは既定のチーム サイト ドキュメント ライブラリ内のフォルダーを取得します。 各[プライベート チャネルは](private-channels.md)、サイトごとに個別のSharePointされます。

会話内で共有されているファイルはドキュメント ライブラリに自動的に追加され、SharePoint で設定されているアクセス許可とファイルのセキュリティ オプションは、Teams 内に自動的に反映されます。 SharePoint でサイト アドレスを変更した場合の影響の詳細については、「[サイト アドレスを変更する](/sharepoint/change-site-address)」を参照してください。

プライベート チャット ファイルは送信者の OneDrive フォルダーに保存され、ファイル共有プロセスの一環としてすべての参加者にアクセス許可が自動的に付与されます。

ユーザーにライセンスが割り当SharePoint場合、ユーザーはユーザーにOneDriveストレージをMicrosoft 365。 ファイル共有は標準チャネルで機能しますが、ユーザーはチャット内のストレージを使用せずにチャットOneDriveファイルを共有Microsoft 365。

ドキュメント ライブラリとドキュメント ライブラリにファイルSharePoint保存OneDrive、組織レベルで構成されたコンプライアンス規則はすべて従います。 

> [!NOTE]
> SharePoint Server との統合は、Teams。

チーム、標準チャネル、ドキュメント ライブラリの関係の例を次に示します。

すべてのチームに対して SharePoint サイトが作成され、**[共有ドキュメント]** フォルダーがチーム用の既定のフォルダーとして作成されます。 **一般** チャネルを含め各標準チャネル (各チームの既定のチャネル) には、**共有ドキュメント** にフォルダーがあります。

![共有ドキュメント フォルダーの図 SharePoint。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

既定のSharePointとドキュメント ライブラリは、別のライブラリに置き換えできません。

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

ユーザーがファイルを共有した場合に既定で表示される共有リンクの種類は、SharePointされます。 詳細については [、「ユーザーが共有用のリンクを取得するときに既定のリンクの種類を変更する」](/sharepoint/change-default-sharing-link) を参照してください。

## <a name="related-topics"></a>関連項目

[SharePointとTeams: より優れた一緒に](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。

[ゲストのエクスペリエンスについて](guest-experience.md)