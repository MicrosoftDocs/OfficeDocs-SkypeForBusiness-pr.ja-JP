---
title: Teams での割り当て
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Microsoft Teams for EducationのMicrosoft Teams管理センターで割り当てを管理する方法について説明します。
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 529240db27824ce8bf872d23636b904198ef7db1
ms.sourcegitcommit: ecc67b7b9378cc72f85517f30c32680045056fda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64504137"
---
# <a name="assignments-in-teams-for-education"></a>教育機関向けの Teams の課題 

Microsoft Teams for Educationの課題と成績の機能を使用すると、教師は学生にタスク、仕事、またはクイズを割り当てることができます。 教育者は、課題のタイムライン、指示、ターンインするリソースの追加、ルーブリックによる採点などを管理できます。 また、[成績] タブでクラスと個々の学生の進行状況を追跡することもできます。

[Microsoft Teams for Educationの課題と成績の詳細については、こちらを参照してください](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)。

> [!Note]
> さまざまなプラットフォームでのTeamsの割り当ての詳細については、プラットフォーム[別のTeams機能に関するページ](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)を参照してください。

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターでの割り当ての統合

Microsoft Teams管理センターの管理者設定を使用すると、組織内の教育者とその学生の機能をオンまたはオフにすることができます。 割り当てに関連する設定を次に示します。

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>毎週の保護者のメール ダイジェスト

保護者向けメールは、各週末に保護者または保護者に送信されます。 メールには、前の週と今後の週の割り当てに関する情報が含まれています。 親と保護者の同期は[、学校データ同期](/schooldatasync/parent-contact-sync)を使用して設定できます。

1. SDS で親と保護者の同期を使用して親連絡先情報をインポートします。 親と保護者の同期を有効にする方法については、「親と保護者の同期 [を有効にする」を](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)参照してください。

2. 既定では設定がオフになっているので、Microsoft Teams管理センターでガーディアン設定をオンにします。 これにより、教師は毎週ダイジェストを送信できるようになります。

   > [!NOTE]
   > 教師は、自分の個人クラス チーム内の設定の選択を解除することで、ダイジェストをオプトアウトできます (**親/保護者のメールの割り当て設定 >**)。

保護者が電子メールを受け取ることを確認するには、次の 3 つの項目に該当する必要があります。

- SDS で学生プロファイルに添付され、 _親_ または _保護者_ としてタグ付けされたメール アドレス。 詳細については、「 [親と保護者の同期ファイル形式」を](/schooldatasync/parent-contact-sync-file-format)参照してください。

- 学生は、 [課題](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)設定で教師が電子メールを無効にしていない少なくとも 1 つのクラスに属しています。

- メールには、前の週または今後の週の期限がある割り当てに関する情報が含まれます。

この機能の既定の設定は - **オフです**。

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode は、すべての学生にコンピューター サイエンスを提供するブロックベースのコーディング プラットフォームです。

MakeCode は、Microsoft の [使用条件](https://go.microsoft.com/fwlink/?LinkID=206977) と [プライバシー](https://go.microsoft.com/fwlink/?LinkId=521839) ポリシーの対象となる Microsoft 製品です。

この機能の既定の設定は - **オフです**。

Teamsで MakeCode の割り当てを有効にするには、**Teams管理センター** に移動し、[**割り当て]** セクションに移動し、[MakeCode] トグル オプションを **[オン]** に切り替えます。 **[保存]** を選択します。 これらの設定を有効にするには、数時間かかります。

この機能の動作の詳細については、この [ビデオデモをご覧](https://makecode.com/blog/teams/teams-assignments)ください。

[MakeCode の詳細については、こちらを参照してください](https://aka.ms/makecode)。

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) は学術的整合性サービスです。 これは、独自の利用規約とプライバシー ポリシーの対象となるサード パーティのサービスです。 お客様は、サードパーティ製品およびサービスの使用について責任を負います。

この機能の既定の設定は - **オフです**。

組織で Turnitin を有効にするには、Turnitin サブスクリプションが必要です。 次に、Turnitin 管理コンソールで確認できる次の情報を入力できます。

- **TurnitinApiKey**: これは、管理コンソールの [統合] の下にある 32 文字の GUID です。
- **TurnitinApiUrl**: これは、Turnitin 管理コンソールの HTTPS URL です。

この情報の取得に役立ついくつかの手順を次に示します。

**TurnitinApiUrl** は、管理コンソールのホスト アドレスです。
例: `https://your-tenant-name.turnitin.com`

管理コンソールでは、統合と、統合に関連付けられた API キーを作成できます。

サイド メニューから **[統合** ] を選択し、[ **統合の追加** ] を選択し、統合に名前を付けます。

![新しい統合の追加を示すスクリーンショット。](./educationImages/Assignments_mopo_turnitin2.png)

プロンプトに従うと **、TurnitinApiKey** が提供されます。
API キーをコピーし、Microsoft Teams管理センターに貼り付けます。  これは、キーを表示できる唯一の時間です。

![API キーのコピーを示すスクリーンショット。](./educationImages/Assignments_mopo_turnitin3.png)

この設定の管理センターで **[保存]** ボタンをクリックすると、これらの設定が有効になるのに数時間かかります。

## <a name="assignments-data"></a>割り当てデータ

課題には、教師と学生の両方によって生成される情報が格納されます。 すべてのデータは、教師と、情報がクラスで意図されている特定の学生の間で共同共有されます。 このデータには、SharePointとSharePointの外部の 2 つのストアがあります。

>[!NOTE]
>読み取り進行状況などのファースト パーティ統合にも、同じルールが適用されます。

### <a name="assignments-data-in-sharepoint-document-libraries"></a>SharePoint ドキュメント ライブラリ内のデータの割り当て

課題の提出に関連付けられている学生のファイルは、ドキュメント ライブラリ (名前: *Student Work*) に格納されます。 教師によって作成され、学生がアクセスできる課題に関連付けられているファイルは、対応するクラス チーム SharePoint サイトの別のドキュメント ライブラリ (名前: *クラス ファイル*) に格納されます。 ファースト パーティ統合では、同じ対応するクラス チーム SharePoint サイトに割り当てデータを格納することもできます (名前: *割り当てタイトル + タイム スタンプ*)。

#### <a name="files-associated-with-the-student"></a>学生に関連付けられているファイル

IT 管理者は、コンテンツ検索ツールを使用して、課題の提出や課題に関連するファイルに関連する学生ファイル (*Student Work*、 *Class Files*、またはその他のファースト パーティ統合ファイル) を検索できます。 たとえば、管理者は組織内のすべてのSharePoint サイトを検索し、検索クエリで学生の名前とクラス名または割り当て名を使用して、データ主体要求 (DSR) に関連するデータを検索できます。

#### <a name="files-associated-with-the-teacher"></a>教師に関連付けられているファイル

IT 管理者は、コンテンツ検索ツールを使用して、課題に関するクラス内の教師が学生に配布する課題やファイルに関連する教師ファイル (*Student Work*、 *Class Files*、またはその他のファースト パーティ統合ファイル) を検索できます。 たとえば、管理者は組織内のすべてのSharePoint サイトを検索し、検索クエリで教師の名前とクラス名または割り当て名を使用して、DSR に関連するデータを検索できます。

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>SharePoint ドキュメント ライブラリの外部でデータを割り当て

割り当てに関連する一部のデータは、クラス チームSharePointサイトに格納されていないため、コンテンツ検索では検出できません。 これには次のものが含まれます。

- 教師からの学生の成績とフィードバック
- 各学生が課題に提出したドキュメントの一覧
- 期限などの割り当ての詳細。
- 読み取り進行状況の文章や学生の発音データなどのファースト パーティ統合データ

この種類のデータの場合、IT 管理者や教師などのデータ所有者は、DSR に関連するデータを見つけるために、クラス チームの割り当てに入る必要があります。 管理者は、自分自身を所有者としてクラスに追加し、そのクラス チームのすべての割り当てを表示できます。

>[!NOTE]
>学生がクラスの一部でなくなった場合でも、そのデータは *登録されなくなった* クラスに存在する可能性があります。 学生は、テナント管理者に、これまで参加していたクラスの一覧を提供する必要があります。

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>SharePoint ドキュメント ライブラリの外部で割り当てデータを一括エクスポートする

#### <a name="for-a-student"></a>学生の場合

1 人の学生のデータを一括エクスポートするには、参加しているクラスから学生を削除する前に [、スクリプトを実行](/microsoft-365/education/deploy/configure-assignments-for-teams) して ``userId``、 . 学生がサイトから削除された場合は、管理者はスクリプトを実行する前に学生をクラスに追加するか、管理者が学生が参加した日時を指定``userId````classId``できます。

学生の提出に関するデータがエクスポートされます。

#### <a name="for-a-teacher"></a>教師の場合

一括エクスポートの割り当てデータは学生と同じように動作しますが、教師がアクセス権を持つすべての提出はエクスポートされます。

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>ドキュメント ライブラリの外部で割り当てデータSharePoint一括削除する

#### <a name="for-a-student"></a>学生の場合

1 人の学生のデータを一括削除するには、参加しているクラスから学生を削除する前に、 [スクリプトを実行](/microsoft-365/education/deploy/configure-assignments-for-teams) して ``userId``、 . 学生がサイトから削除された場合は、管理者はスクリプトを実行する前に学生をクラスに追加するか、管理者が学生が参加した日時を指定``userId````classId``できます。

a を ``ClassId`` 指定すると、管理者は特定のクラスから学生に関する情報のみを削除できます。

#### <a name="for-a-teacher"></a>教師の場合

教師の割り当てのデータはクラス間で共有されるため、一括削除オプションはありません。 代わりに、管理者は自分自身をクラスに追加し、アプリに移動して、割り当てを削除できます。

詳細については、「 [Teamsの割り当ての構成」を](/microsoft-365/education/deploy/configure-assignments-for-teams)参照してください。

## <a name="removing-assignments-and-grades"></a>課題と成績の削除

Teams ポリシーを使用して、特定のユーザーまたはテナント全体の割り当てと成績を削除することもできます。

個々のユーザーの割り当てと成績を削除するには、**管理センター Teams** 移動し、**Teams アプリ>アクセス許可ポリシー** に移動して、新しいアプリアクセス許可ポリシー定義を作成します。  新しいポリシー定義を作成するときは、Microsoft アプリ ポリシーを [特定 **のアプリ** をブロックする] に設定 _し、他のすべてのアプリを許可_ し、ブロックされたアプリケーションの一覧に **割り当てを** 追加します。 新しいポリシー定義を保存したら、適切なユーザーに割り当てます。

テナント全体の課題と成績を削除するには、**Teams管理センター** に移動し、**Teams アプリ>アプリの管理** に移動し、アプリケーションの一覧から **課題** を検索して選択します。 [割り当てアプリケーション設定] ページ内の状態設定を _[ブロック]_ に変更します。

## <a name="assignments-diagnostic-tool-for-users"></a>ユーザーの割り当て診断ツール

Microsoft サポートは、割り当て機能に関連する問題を調査するために、Microsoft エンジニアリング チームの診断データを収集するツールを作成しました。

このツールは、ユーザーが問題を発生する画面で、割り当ての内部でアクセスできます。

Teamsで診断ツールをプルアップするには、次の操作を実行できます。

- **デスクトップと Web の場合:**
  - Ctrl + / を選択する
- **モバイル デバイスの場合:**
  - 2 本の指で画面をタッチし、指を 45 度回転させるか、または
  - 3 本の指で 15 秒間画面をタップする

診断ツールがポップアップ表示されると、Microsoft テクニカル サポートに必要なデータの一覧がユーザーに表示されます。

プルされるデータには、次のものが含まれる場合があります。

- グループ ID
- テナント ID
- セッション ID
- 割り当て ID
- 申請 ID
- ユーザー ID

このデータは自動的に Microsoft に送信されません。 ユーザーは、サポート チケットに関するデータをコピーして Microsoft サポート エージェントに貼り付ける必要があります。

ユーザーが診断ツールをプルアップした後、それを閉じると、データは送信されません。

データが Microsoft サポート エージェントに送信されると、組織のMicrosoft 365サービス契約に基づくサポート データとして処理されます。

教育者や学生と共有できるこの診断ツールの使用方法については、「 [課題のトラブルシューティングに関する診断データを取得する](https://support.microsoft.com/topic/b40793f5-dbae-4c8a-841a-6baa7f232e2e)」を参照してください。
