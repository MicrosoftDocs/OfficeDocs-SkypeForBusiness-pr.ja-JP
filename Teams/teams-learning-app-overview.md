---
title: Teams ラーニング アプリのインストール、管理、アクセス許可の割り当て (プライベート プレビュー)
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: Microsoft Teams ラーニング アプリを使用して、従業員が組織全体のコンテンツ ライブラリを共有、割り当て、学習できる学習のための中心的なハブを作成します。
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703458"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a>Teams ラーニング アプリのインストール、管理、アクセス許可の割り当て (プライベート プレビュー)

*この記事には、プライベート プレビューの Teams ラーニング アプリの暫定コンテンツが含まれている。*

Microsoft Teams ラーニング アプリ (プライベート プレビュー) を使用すると、組織内のチームや個人が 1 日の自然な部分で学習することができます。 このアプリは、Teams の中央ハブを作成し、従業員が組織全体のコンテンツ ライブラリを共有、割り当て、学習できる場所です。 管理者は、アプリのアクセス許可を設定し、学習コンテンツ ソースを許可します。 学習コンテンツには、LinkedIn ラーニング、Microsoft Learn、Microsoft 365 のトレーニング、SharePoint Online に保存されている組織独自のコンテンツ、アプリでサポートされているサードパーティ プロバイダーが含まれます。

Teams ラーニング アプリ (プライベート プレビュー) をセットアップするには、次の必要があります。

-   Teams 管理センターの管理
-   Microsoft 365 管理センターの管理 (グローバル管理者)
-   グローバル管理者 (IT 管理者または Microsoft 365 管理者とも呼ばれる) が組織内のすべてのユーザーに割り当て可能な、ナレッジ管理者 (Microsoft 365 管理センターの新しい役割)。 この役割は、Microsoft 365 管理センターを通じて組織の学習コンテンツ ソースを管理します)。 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a>Teams 管理センターで Teams ラーニング アプリ (プライベート プレビュー) を管理する

Teams 管理者は、Teams ラーニング アプリ (プライベート プレビュー) をアプリ ストアからインストールし、Teams 管理センターからアプリのセットアップ、管理、アクセス許可のポリシーを適用します。

### <a name="manage-the-teams-learning-app-private-preview"></a>Teams ラーニング アプリを管理する (プライベート プレビュー)

アプリの設定を管理するには、次の手順を実行します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。

   ![Teams アプリと [アプリの管理] セクションが表示されている Teams 管理センターの左側のナビゲーション](media/learning-app-teams-manage-apps-nav.png)

2. [アプリ **の管理] ページ** の検索ボックスに、Teams ラーニング アプリ (プライベート プレビュー) を検索する学習を入力します。 

   ![検索ボックスが表示されている Teams 管理センターの [アプリの管理] ページ](media/learning-app-teams-manage-apps-page.png)

3. [学習] **ページで、次の方法を実行** します。
   1. [ **状態]** で[ **許可] を選** び、アプリを有効にできます。
   2. [設定 **] タブ** の [ **アプリの設定** ] セクションで、Microsoft 365 管理センターに移動して、学習コンテンツ ソースを構成します。

   ![[状態] セクションと [アプリの設定] セクションが表示されている Teams 管理センターの [学習] ページ](media/learning-app-teams-learning-page.png)

4. アプリ **の設定を管理** した後、[アクセス許可とセットアップ ポリシー] に移動して、組織がプライベート プレビューに参加する一部としてアプリにアクセスできる必要がある従業員にアクセス許可を付与します。

> [!NOTE]
>  組織が Teams TAP100 プログラムの一部としてリング 4.0 を使用している場合は、次の操作を行って、リング 3.0 の承認済みユーザーが Teams ラーニング アプリ (プライベート プレビュー) にアクセスできる場合があります。

プライベート プレビューの一環として、Teams ラーニング アプリ (プライベート プレビュー) はリング 3.0 でリリースされます。 組織がリング 4.0 の場合、アプリはアプリ ストアに表示されます。 アプリをテストするには、カスタム アプリのアクセス許可ポリシーを作成し、それを[すべてのアプリを許可する] に設定して、承認されたユーザーをリング 3.0 に割り当てる必要があります。

   ![[すべてのアプリを許可する] が選択されている TAP-AppsPermission-Plcy ページ](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで学習コンテンツ ソースを構成する

Microsoft 365 管理センターの管理者は、自分自身または組織内の選択した個人にナレッジ管理者の役割を割り当て、Teams ラーニング アプリ (プライベート プレビュー) に関連する設定を管理し、学習コンテンツ ソースを構成できます。

> [!TIP]
> 知識管理者は、中程度の技術的な知識を持ち、既存の SharePoint 管理者資格情報を持っている必要があります。できれば、組織の教育、学習、トレーニング、または従業員の経験に精通しているユーザーが必要です。
 
管理者は、アプリで利用できる学習コンテンツ ソース (LinkedIn ラーニングや SharePoint など) を選択します。 次に、管理者は、コンテンツが検索と検出に使用できる情報であり、アプリを使用する従業員が参照できるよう、これらのソースを構成します。

### <a name="assign-the-knowledge-admin-role-optional"></a>サポート技術情報管理者の役割を割り当てる [オプション]

これらの手順は、Microsoft 365 管理センターの管理者が実行する必要があります。

1.  Microsoft 365 管理センターの左側のナビゲーションで、[ロール] に移動 **します**。

2.  [ロール **] ページの** **[Azure** AD] タブで、[サポート技術情報の **管理者] を選択します**。
 
3.  [サポート **技術情報の管理**] ページの [割り当てられた管理者] セクションで、[追加] を選択し、役割に選択したユーザーを追加します。

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a>アプリの学習コンテンツ ソースの設定を構成する

これらの手順は、Microsoft 365 管理者またはサポート技術情報の管理者が実行する必要があります。

1.  Microsoft 365 管理センターの左側のナビゲーションで、[組織の設定 **] 設定に**  >  **移動します**。

2.  [設定 **] ページ** の [サービスとアドイン **] &** 学習アプリを **選択します**。

   ![学習アプリが表示されている Microsoft 365 管理センターの [設定] ページ](media/learning-app-365-settings-page.png)

3.  [学習 **アプリ] パネル** で、組織用に構成する学習コンテンツ ソースを選択し、[保存] を選択 **します**。

   ![コンテンツ ソースのオプションを表示する Microsoft 365 管理センターの [学習アプリ] パネル](media/learning-app-365-settings-learning-app-panel.png)

存在するすべての学習ソースの中には、既定で有効になっているものがあります。 これには次のものが含まれます。

- LinkedIn ラーニング (無料コンテンツ)
- Microsoft Learn
- Microsoft 365 トレーニング

> [!NOTE]
> 組織に LinkedIn ラーニング標準または Pro サブスクリプションがある場合、組織内の従業員のコンテンツ リポジトリのロックが解除されます。 アクセス許可を持つ従業員だけがコンテンツ リポジトリ全体を使用できます。

その他のソースは、手動で有効または構成する必要がある場合があります。 Microsoft から提供されていない学習資料のライセンスは、お客様の組織と第三者の間で別途ライセンスされます。 ユーザーの学習にサインアップしたユーザーを確認する必要があります。

学習コンテンツ ソースを有効または無効にするには、ソースの横にあるチェック ボックスをオンにします。 ソースが有効な場合は、チェック マークが表示されます。

## <a name="configure-sharepoint-as-a-learning-content-source"></a>学習コンテンツ ソースとして SharePoint を構成する

Microsoft 365 管理センターで、Teams ラーニング アプリ (プライベート プレビュー) の学習コンテンツ ソースとして SharePoint を構成します。

### <a name="overview"></a>概要

ナレッジ管理者は、ラーニング サービスが構造化された SharePoint リストの形式で空の一元管理された学習コンテンツ リポジトリを作成できるサイト URL を提供します。 このリストは、組織が学習コンテンツを含む会社間の SharePoint フォルダーへのリンクを格納するために使用できます。 管理者は、フォルダーの URL リストを収集し、管理する必要があります。 これらのフォルダーには、Teams ラーニング アプリ (プライベート プレビュー) で利用できるコンテンツのみを含める必要があります。

### <a name="permissions"></a>アクセス許可

フォルダー URL は、組織内のすべての SharePoint サイトから収集できます。 これらのフォルダー内のコンテンツは検索できますが、使用できるのは、個々の従業員がアクセス許可を持っているコンテンツのみです。
 
### <a name="learning-service"></a>ラーニング サービス

ラーニング サービスは、提供されたフォルダー URL を使用して、これらのフォルダーに保存されているすべてのコンテンツからメタデータを取得します。 一元管理されたリポジトリにフォルダー URL を指定して 24 時間以内に、従業員はアプリ内で会社のコンテンツを検索して使用できます。 リポジトリからのコンテンツの削除は、現時点ではサポートされていません。 意図せず表示されたコンテンツは、Microsoft 365 管理センターで新しい SharePoint サイトの URL を指定することでのみ削除できます。

### <a name="configure-sharepoint-as-a-source"></a>SharePoint をソースとして構成する

これらの手順は、Microsoft 365 管理者またはサポート技術情報の管理者が実行する必要があります。

1.  Microsoft 365 管理センターの左側のナビゲーションで、[設定] に移動 **します**。
 
2.  [設定 **] ページ** の [サービスとアドイン **] &** 学習アプリを **選択します**。

   ![学習アプリが表示されている Microsoft 365 管理センターの [設定] ページ](media/learning-app-365-settings-page.png)

3.  [学習 **アプリ] パネル** で、アプリで一元管理されたリポジトリを作成する SharePoint サイトのサイト URL を指定します。

   ![SharePoint が選択されている Microsoft 365 管理センターの [学習アプリ] パネル](media/learning-app-365-panel-sharepoint-selected.png)

4.  SharePoint リストは、指定された組織の SharePoint サイト内に自動的に作成されます。 SharePoint サイトの左側のナビゲーションで、[学習アプリ コンテンツ リポジトリ **] を選択します**。 

   ![[学習アプリ コンテンツ リポジトリ] セクションが表示されている SharePoint の左のナビゲーション](media/learning-app-content-repository-nav.png)

 
5. [ラーニング **アプリ コンテンツ リポジトリ] ページ** で、SharePoint リストに学習コンテンツ フォルダーの URL を入力します。

   1.   [新規 **] を** 選び、[新しい **アイテム] パネルを表示** します。 

   ![[新規] オプションが表示された SharePoint の [学習アプリ コンテンツ リポジトリ] ページ](media/learning-app-content-repository-new.png)
 
   2.   [新 **しいアイテム]** パネルの [ **タイトル** ] フィールドで、選択したディレクトリ名を追加します。 [フォルダー **URL] フィールド** で、学習コンテンツ フォルダーに URL を追加します。 **[保存]** を選択します。

   ![SharePoint の [タイトル] フィールドと [フォルダーの URL] フィールドを示す新しいアイテム パネル](media/learning-app-new-item-panel.png)

   3. [学習アプリ コンテンツ リポジトリ] ページが更新され、新しい学習コンテンツが表示されます。

   ![更新された情報を表示する SharePoint の [学習アプリ コンテンツ リポジトリ] ページ](media/learning-app-content-repository-populated.png)


 


