---
title: Microsoft Teams でのパブリック プレビュー
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn about the public preview in Microsoft Teams. Try out new features and provide feedback.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: ffdd34d8a36726d96bc44ae766e91ca6ae77280b
ms.sourcegitcommit: b535a70df5bc842f597889582df3eb86371f8139
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2022
ms.locfileid: "68869592"
---
# <a name="microsoft-teams-public-preview"></a>Microsoft Teams パブリック プレビュー

> [!NOTE] 
> プレビューに含まれている機能は完全でないため、一般公開前に変更される場合があります。 これらは、評価と調査のみを目的としています。 プレビュー機能は、Office 365 Government Community Cloud (GCC) ではサポートされていません。

Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.

Teams パブリック プレビューで利用できる内容の一覧については、[Microsoft Teams パブリック プレビューの技術ノート](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview)、[Teams 管理機能のリリース ノート](/OfficeUpdates/teams-admin)、[および Office Current Channel のリリース ノート (プレビュー)](/officeupdates/current-channel-preview) に関するページを参照してください。

## <a name="set-the-update-policy"></a>更新ポリシーを設定する

Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy. Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app. You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users. The policy needs to be assigned to specific users because it doesn't over-write the global policy.

1. [Microsoft Teams 管理センター](https://admin.teams.microsoft.com/)にサインインする。

2. **Teams** > **Teams 更新ポリシー** を選択します。

1. **[追加]** を選択して新しいポリシーを作成するか、既存のポリシーを選択して **[更新ポリシー]** を開きます。

2. 更新ポリシーに名前を付け、説明を追加し **[プレビュー機能の表示]** の設定を選択します。

   -   **Office Preview をフォローする** (既定)
       - この新しい既定のオプションでは、Office 最新チャネル (プレビュー) に登録されているすべてのユーザーに対して、Teams パブリック プレビュー機能を自動的に有効にします。 
       - エンド ユーザーが必要とするアクションはもうありません。
   -   **有効**
       - このオプションは、ユーザーが Office 最新機能提供チャネル (プレビュー) に登録しているかどうかに関わらず、Teams パブリック プレビューを有効にします。 
       - エンド ユーザーは、Teams アプリで Teams パブリック プレビューに参加することも必要です。

   > [!NOTE]  
   > Teams パブリック プレビューに存在する既存のユーザーで、**最新機能提供チャネル (プレビュー)** に存在しない場合、IT 管理者は、既定の **[Office Preview をフォローする]** から **[有効]** に切り替える必要があります。
 
   - **無効** 
     - エンド ユーザーは Teams パブリック プレビュー機能を使用できません。

    ![プレビュー設定ダイアログが表示されます。](media/public-preview-policy.png)  

また、`-AllowPublicPreview` パラメーターを含む PowerShell `Set-CsTeamsUpdateManagementPolicy` コマンドレットを使用してポリシーを設定することもできます。

## <a name="enable-public-preview"></a>パブリック プレビューを有効にする

デスクトップまたは Web クライアントでパブリック プレビューを有効にするには、次のタスクを完了する必要があります。

1. プロフィールの左側にある 3 つのドットを選択して、[Teams] メニューを表示します。
2. **[情報]** > **[パブリック プレビュー]** を選択します。
3. **[パブリック プレビューに切り替える]** を選択します。

> [!NOTE]  
> このオプションは、**[プレビュー機能の表示]** が **[有効]** に設定されている場合のみ利用可能です。

### <a name="public-preview-for-microsoft-teams-rooms-on-windows"></a>Windows の Microsoft Teams Rooms のパブリック プレビュー

パブリック プレビューは既定でオフになっています。 パブリック プレビューがオンの場合、エンドユーザーは有効な Teams Rooms のパブリック プレビューにある機能にアクセスできます。 パブリック プレビューをオンにするには、XML 構成ファイルに ```<EnablePublicPreview>True</EnablePublicPreview>``` を追加します。

パブリック プレビューに 5 - 10 台のデバイスを登録することをお勧めします。 

すべてのパブリック プレビュー機能は、[Microsoft Teams パブリック プレビュー - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview) で発表されます。

## <a name="teams-now-follows-office-preview-users"></a>Office Preview ユーザーを Teams がフォロー

新しいグローバル ポリシーの既定である **[Office Preview をフォローする]** は、Windows および Mac の Office 365 クライアントの最新機能提供チャネル (プレビュー) にユーザーが存在する場合、ユーザーは自動的に Teams のパブリック プレビュー チャネル参加するることができます。

Microsoft Office は引き続き最新機能提供チャネル (プレビュー) から、Teams クライアントはパブリック プレビュー チャネルから更新プログラムを受け取ります。 このポリシーは、Teams チャネルに基づいて Office チャネルを切り替えるものではありません。 

**Office 最新機能提供チャネル (プレビュー) を使用していない Teams の既存のプレビュー ユーザーを保持するにはどうすればいいですか?**

Teams パブリック プレビューへのオプトインまたはオプトアウトできる既存のユーザーで、その設定を現在の形のまま維持したい場合は、新しい既定の **[Office Preview をフォローする]** を **[有効]** に変更する必要があります ([更新ポリシーの設定](#set-the-update-policy)を参照してください)

**この設定をオプトアウトするにはどうすればいいですか?**

Teams 管理センターで、**[Office Preview をフォローする]** から **[無効]** にして、設定を無効にすることができます ([更新ポリシーの設定](#set-the-update-policy)を参照してください)

## <a name="related-topics"></a>関連項目

[開発者向けパブリック プレビュー](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
