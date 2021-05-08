---
title: Microsoft 楽楽学習 (プライベート プレビュー) のインストール、管理、アクセス許可の割り当て
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
description: Microsoft Central Learning (プライベート プレビュー) を使用して、従業員が組織全体でコンテンツ ライブラリを共有、割り当て、学習できる学習の中心ハブを作成します。
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3b99cdcd49dc35a558d6217e28bf57bbb8563827
ms.sourcegitcommit: b56727299d7ea47e23807114a4f5881e289c0b6a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2021
ms.locfileid: "51880381"
---
# <a name="install-manage-and-assign-permissions-for-microsoft-viva-learning-private-preview"></a>Microsoft 楽楽学習 (プライベート プレビュー) のインストール、管理、アクセス許可の割り当て

*この記事には、プライベート プレビュー段階にある、Microsoft の事前コンテンツが含まれているとします。*

Microsoft Learning (プライベート プレビュー) は、組織内のチームや個人が一日の自然な部分で学習を行える機能を提供します。 このアプリは、組織内のコンテンツ ライブラリTeams共有、割り当て、学習できる中央ハブを作成します。

管理者は、アクセス許可を設定し、Learning Learning (プライベート プレビュー) の学習コンテンツ ソースを許可します。 学習コンテンツには、LinkedIn Learning、Microsoft Learn、Microsoft 365 トレーニング、SharePoint オンラインに保存されている組織独自のコンテンツ、およびInved Learning (プライベート プレビュー) でサポートされているサードパーティ プロバイダーが含まれます。

## <a name="admin-roles"></a>管理者ロール

(プライベート プレビュー) に対して、次のアクセス許可を設定するには、次のアクセス許可が必要です。

- Microsoft Teams管理者
- Microsoft 365管理者または管理者SharePointする
- ナレッジ管理者 - 組織内のすべてのユーザーに割り当てMicrosoft 365管理センターでの新しいロールです。 このロールは、管理センターで組織のラーニング コンテンツ ソースMicrosoft 365管理します。 

> [!TIP]
> ナレッジ管理者は、中程度の技術的な知識を持ち、既存の SharePoint 管理者の資格情報を持っている必要があります。できれば、組織の教育、学習、トレーニング、または従業員の経験に精通しているユーザーです。
 
## <a name="manage-viva-learning-private-preview-in-the-teams-admin-center"></a>Teams 管理センターで、このビデオを使って、Teams Learning を管理します。

管理者Teamsアプリ ストアから、Teams Learning (プライベート プレビュー) をインストールした後、Teams 管理センターを通じてセットアップ、管理、およびアクセス許可ポリシーを適用します。

### <a name="manage-settings-for-viva-learning-private-preview"></a>(プライベート プレビュー) の[楽楽学習] の設定を管理する

これらのタスクを実行するには、管理センター Teams管理者である必要があります。

楽楽学習の設定を管理するには、次の手順に従います。

1. 管理センターの左側のナビゲーションでTeamsアプリの管理Teams **に**  >  **移動します**。

   ![[アプリの管理] Teams管理] セクションが表示Teams左側のナビゲーション](media/learning-app-teams-manage-apps-nav.png)

2. [アプリ **の管理] ページ** の検索ボックスに、「learning」と入力して、Teams ラーニング アプリ (プライベート プレビュー) を検索します。 

   ![検索ボックスが表示されている Teams管理センターの [アプリの管理] ページ](media/learning-app-teams-manage-apps-page.png)

3. [学習] **ページで、次の方法を** 実行します。
   1. [ **状態]** で、[ **許可] を選択** してアプリを有効にしてください。
   2. **[設定]** タブの [アプリの設定] セクションで、Microsoft 365 管理センターに移動して、学習コンテンツ ソースを構成します。

   ![[状態] セクションと [Teams設定] セクションが表示されている管理センターの [学習] ページ](media/learning-app-teams-learning-page.png)

4. [**アプリ設定の** 管理]の後、[アクセス許可とセットアップ ポリシー] に移動して、組織のプライベート プレビューへの参加の一環としてアプリにアクセスする必要がある従業員にアクセス許可を付与します。

> [!NOTE]
>  組織が Teams TAP100 プログラムの一部としてリング 4.0 に参加している場合は、Ring 3.0 で承認されたユーザーが Ring Learning (プライベート プレビュー) にアクセスするには、次の操作を行う必要があります。

プライベート プレビューの一環として、Ring 3.0 では、Ring Learning (プライベート プレビュー) がリリースされます。 組織が Ring 4.0 の場合は、アプリ ストアにアプリが表示されます。 アプリをテストするには、カスタム アプリのアクセス許可ポリシーを作成し、[すべてのアプリを許可する] に設定して、それを Ring 3.0 承認済みユーザーに割り当てる必要があります。

   ![[すべてのアプリを許可する] が選択されている TAP-AppsPermission-Plcy ページ](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>管理センターで学習コンテンツ ソースMicrosoft 365構成する

Microsoft 365 管理センターの管理者は、自分自身で、または組織内の選択した個人にナレッジ管理者ロールを割り当てる方法で、Learning Learning (プライベート プレビュー) に関連する設定を管理し、学習コンテンツ ソースを構成できます。

管理者は、追加の学習コンテンツ ソース (SharePoint やサポートされているサード パーティのコンテンツ プロバイダー ソースなど) を選択し、その他のコンテンツ ソースを、このユーザーに対して使用できます(プライベート プレビュー)。 管理者は、これらのソースを構成して、コンテンツが検索と検出に使用可能であり、また、このコンテンツを、このユーザーが参照できるよう構成します(プライベート プレビュー)。

> [!NOTE]
>  ユーザーは、Microsoft および LinkedIn Learning 以外のユーザーにサインインProまたは埋め込みビューアーで学習を行います。 この構成済みの学習には、組織とサード パーティの間で個別のライセンス、プライバシー、サービス条項が適用されます。また、このライセンス条項 (プライベート プレビュー) 条項は適用されません。 この種類の学習を選択する前に、組織とユーザーに対して契約が締結されていないことを確認してください。

### <a name="assign-the-knowledge-admin-role-optional"></a>ナレッジ管理者ロールを割り当てる [省略可能]

これらのタスクを実行するにはMicrosoft 365管理者である必要があります。

Learning Learning のナレッジ管理者を割り当てるには、次の手順に従います。

1.  管理センターの左側のナビゲーションMicrosoft 365、[ロール] に **移動します**。

2.  [ロール **] ページ** の **[Azure** AD] タブで、[ナレッジ管理者] **を選択します**。
 
3.  [ナレッジ管理者 **] ページ** の[割り当て管理者] セクションで、[追加] を選択し、ロールに選択したユーザーを追加します。

### <a name="configure-settings-for-the-learning-content-sources-for-viva-learning-private-preview"></a>Learning Learning のラーニング コンテンツ ソースの設定を構成する (プライベート プレビュー)

これらのタスクを実行するにはMicrosoft 365管理者またはナレッジ管理者である必要があります。

Learning Content Sources の設定を構成するには、次の手順に従います。

1.  管理センターの左側のナビゲーションMicrosoft 365、[組織の設定]**設定**  >  **に移動します**。

2.  [組織の **設定] ページ** の [サービス **] タブで** 、[学習アプリ (プレビュー) ] **を選択します**。

     ![設定表示されている Microsoft 365 管理センターの [学習] ページ](media/learning-sharepoint-configure1.png)

3.  [ **学習アプリ (プレビュー)** ] パネルで、組織用に構成する学習コンテンツ ソースを選択し、[保存] を選択 **します**。

     ![コンテンツ ソースのオプションをMicrosoft 365管理センターの学習パネル](media/learning-sharepoint-configure2.png)

存在するすべてのラーニング ソースの中で、既定で有効になっているものがあります。 これには次のものが含まれます。

- LinkedIn Learning (無料コンテンツ)
- Microsoft Learn
- Microsoft 365トレーニング

> [!NOTE]
> 組織に LinkedIn Learning Standard または Pro サブスクリプションがある場合は、組織内の従業員のコンテンツ リポジトリのロックが解除されます。 アクセス許可を持つ従業員だけが、コンテンツ リポジトリ全体を使用できます。 <br>その他のソースは、手動で有効または構成する必要がある場合があります。 Microsoft から提供されていないラーニング ソースは、お客様の組織と第三者の間で個別にライセンスされます。 ユーザーとユーザーの学習にサインアップ済みである必要があります。

学習コンテンツ ソースを有効または無効にするには、ソースの横にあるチェック ボックスをオンにします。 ソースが有効になっている場合は、チェック マークが表示されます。

## <a name="configure-sharepoint-as-a-learning-content-source"></a>学習SharePointソースとしてコンテンツ を構成する

組織のコンテンツSharePoint、組織独自のコンテンツを、Learning Learning (プライベート プレビュー) で利用できるよう、学習コンテンツ ソースとして構成できます。

### <a name="overview"></a>概要

ナレッジ管理者 (またはグローバル管理者) は、Learning Service が空の一元化された場所 (Learning App コンテンツ リポジトリ) を構造化された SharePoint リストの形式で作成できるサイト URL を提供します。 このリストは、組織が、学習コンテンツを含む複数のSharePointリンクを保存するために使用できます。 管理者は、フォルダーの URL の一覧を収集およびキュレーションする責任を負います。 これらのフォルダーには、同じコンテンツのみを含める必要があります。このコンテンツは、このフォルダーを含む必要があります。このコンテンツは、このフォルダーを含む必要があります(プライベート プレビュー)。

「Learning Learning (プライベート プレビュー)」では、次のドキュメントの種類がサポートされています。

- Word、PowerPoint、Excel、PDF
- オーディオ (.m4a)
- ビデオ (.mov、.mp4、.avi)

詳細については、オンライン のドキュメント[SharePoint参照してください](https://docs.microsoft.com/sharepoint/introductionlink)。 

### <a name="permissions"></a>アクセス許可

ドキュメント ライブラリ のフォルダー URL は、組織内のSharePointサイトから収集できます。 既存のすべてのコンテンツ のアクセス許可に従って、このビデオ (プライベート プレビュー) を実行します。 そのため、ユーザーがアクセス許可を持っているコンテンツだけが、検索可能であり、また、このコンテンツは、このコンテンツを、プライベート プレビュー (プライベート プレビュー) で検索および表示できます。 これらのフォルダー内のコンテンツは検索可能ですが、個々の従業員がアクセス許可を持っているコンテンツのみを使用できます。

組織のリポジトリからのコンテンツの削除は現在サポートされていません。

意図せず表示されたコンテンツを削除するには、次の手順に従います。

1.  ドキュメント ライブラリのアクセスを制限するには、[アクションの表示] **オプション** を選択し、[アクセスの管理] **を選択します**。
     
     ![[アクセスの管理] SharePoint表示されているドキュメント ライブラリ ページ。](media/learning-sharepoint-permissions2.png)

2.  ドキュメント ライブラリ内の元のドキュメントを削除します。

詳細については、「最新のエクスペリエンスでの共有とアクセス許可[SharePoint参照してください](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)。 

### <a name="learning-service"></a>Learning Service

Learning Service は、指定されたフォルダー URL を使用して、これらのフォルダーに格納されているすべてのコンテンツからメタデータを取得します。 一元化されたリポジトリにフォルダー URL を指定して 24 時間以内に、従業員は、組織のコンテンツを検索して、その組織のコンテンツを、InSved Learning (プライベート プレビュー) 内で使用できます。 更新されたメタデータやアクセス許可を含むコンテンツに対する変更はすべて、24 時間以内に Learning Service にも適用されます。

### <a name="configure-sharepoint-as-a-source"></a>ソースSharePoint構成する

これらのタスクを実行するには、Microsoft 365管理者、SharePoint、またはナレッジ管理者である必要があります。

「SharePoint Learning (プライベート プレビュー)」で学習コンテンツ ソースとして構成するには、次の手順に従います。

1.  管理センターの左側のナビゲーションMicrosoft 365、[組織の設定]**設定**  >  **に移動します**。
 
2.  [組織の **設定] ページ** の [サービス **] タブで** 、[学習アプリ (プレビュー) ] **を選択します**。

     ![設定ページに[Microsoft 365 Learning] と表示されます。](media/learning-sharepoint-configure1.png)

3.  [Learning **app (Preview)] パネル** の **[SharePoint]** で、一元化されたリポジトリを作成する SharePoint サイトへのサイト URL を指定します。

     ![[管理センター] の [Microsoft 365] パネルで、選択したSharePoint表示されます。](media/learning-sharepoint-configure2.png)

4.  指定SharePointリストは、指定されたサイト内にSharePointされます。

     ![新しく作成SharePointサイト内のSharePoint一覧。](media/learning-sharepoint-configure3.png)

     サイトの左側のナビゲーションで、[サイト コンテンツSharePoint アプリ **コンテンツ** リポジトリ]  >  **を選択します**。 

     ![SharePointコンテンツ ナビゲーションと [Learning App Content Repository] セクションを表示する一覧を表示します。](media/learning-sharepoint-configure4.png) 

5. [Learning **App Content Repository]** ページで、SharePointコンテンツ フォルダーの URL を入力します。

   1. [新規 **] を** 選択して[新しい **アイテム] パネルを** 表示します。 

       ![[新規] オプションが表示SharePointコンテンツ リポジトリの学習ページ。](media/learning-sharepoint-configure5.png)
 
   2. [新 **しいアイテム]** パネルの [タイトル] **フィールドに** 、選択したディレクトリ名を追加します。 [フォルダー **URL] フィールド** で、学習コンテンツ フォルダーに URL を追加します。 **[保存]** を選択します。

       ![[タイトル] フィールドと [SharePoint URL] フィールドが表示されている新しいアイテム パネル。](media/learning-sharepoint-configure6.png)

   3. [ **学習アプリ コンテンツ リポジトリ] ページ** が、新しい学習コンテンツで更新されます。

       ![[学習コンテンツ リポジトリ] ページSharePoint情報が表示されます。](media/learning-sharepoint-configure7.png)

> [!NOTE]
> Learning App Content Repository へのより広範なアクセスを可能にするために、リストへのリンクは、ユーザーがアクセスを要求し、最終的にリストを設定するのに役立つ、近い間に、一覧へのリンクを、同じ Learning (プライベート プレビュー) インターフェイスで利用できます。 サイト所有者とグローバル管理者は、リストへのアクセス権を付与する必要があります。 Access はリストにのみ固有であり、リストが保存されているサイトには適用されません。

### <a name="folder-url-document-library-curation"></a>フォルダー URL ドキュメント ライブラリのキュレーション

Microsoft Graph API によって、既定のメタデータ (変更日、作成者、ドキュメント名、コンテンツ タイプ、組織名など) が自動的に、このメタデータが、自動的に「Learning」(プライベート プレビュー) に取り込まれます。
 
コンテンツの全体的な検出と検索の関連性を向上させるために、[説明] 列を追加することをお **勧** めします。

ドキュメント ライブラリ ページ **に [説明]** 列を追加するには、次の手順に従います。

1.  [ドキュメント] **ページで、[** 列の追加] **を選択します**。

2. [アクションの **表示] オプションを** 選択し、[1 行 **のテキスト] を選択します**。

     ![[ドキュメント] ページSharePoint行が強調表示された [アクションの表示] オプションが表示されます。](media/learning-sharepoint-curation1.png)

3. [列 **の作成] パネル** の [名前] **フィールドに** 、列のわかりやすい名前を追加します。 **[保存]** を選択します。

     ![[名前] と他のフィールドSharePoint列パネルを作成します。](media/learning-sharepoint-curation2.png)
 
4. [ドキュメント **] ページ** の [説明] **列** で、各アイテムのカスタム説明を追加します。 説明が指定されていない場合は、既定のメッセージが表示され、コンテンツが独自のライブラリからの内容として強調表示SharePointされます。 

     ![[説明] 列SharePoint説明が表示されているドキュメント ページ。](media/learning-sharepoint-curation3.png)
 
