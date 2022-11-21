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
description: Microsoft Teams for Educationの Microsoft Teams 管理センターで割り当てを管理する方法について説明します。
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1475406697778080d5e49aae58729e6eb1d1576c
ms.sourcegitcommit: 9504b7a67e593f5575060b09b69817325e2a1f77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2022
ms.locfileid: "69111144"
---
# <a name="assignments-in-teams-for-education"></a>教育機関向けの Teams の課題 

Microsoft Teams for Educationの課題と成績の機能を使用すると、教師はタスク、作業、またはクイズを学生に割り当てることができます。 教師は、課題のタイムラインの管理、指示の管理、ターンインするリソースの追加、ルーブリックによる採点などを行うことができます。 また、[成績] タブでクラスと個々の学生の進捗状況を追跡することもできます。

[Microsoft Teams for Educationの課題と成績の詳細については、こちらをご覧ください](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)。

> [!Note]
> さまざまなプラットフォームでの Teams の割り当ての詳細については、「 [プラットフォーム別の Teams 機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでの割り当ての統合

Microsoft Teams 管理センターの管理者設定を使用して、組織内の教師とその学生の機能をオンまたはオフにすることができます。

割り当ての設定を表示および管理するには、Teams 管理センターの <a href="https://admin.teams.microsoft.com/education/assignments-settings" target="_blank">**[Education****Assignment settings]\(** 教育 > の割り当て設定</a>\) に移動します。

割り当てに関連する設定を次に示します。

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>週単位の保護者メール ダイジェスト

保護者のメールは週末に保護者または保護者に送信されます。 電子メールには、前の週と今後の週の割り当てに関する情報が含まれています。 保護者と保護者の同期は、 [School Data Sync](/schooldatasync/parent-contact-sync) を使用して設定できます。

1. 親の連絡先情報を SDS の親同期とガーディアン同期を使用してインポートします。 親と保護者の同期を有効にする方法については、「 [親と保護者の同期を有効にする](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)」を参照してください。

2. 設定が既定でオフになっているので、Microsoft Teams 管理センターでガーディアン設定を有効にします。 これにより、教師は毎週ダイジェストを送信できます。

   > [!NOTE]
   > 教師は、自分の個人用クラス チーム内の設定 (**[割り当て設定] > [親/保護者の電子メール**]) の選択を解除することで、ダイジェストをオプトアウトできます。

保護者がメールを受け取ることを確認するには、次の 3 つの項目が true である必要があります。

- Emailアドレスは、SDS の学生プロファイルに添付され、_親_ または _保護者_ としてタグ付けされます。 詳細については、「 [親と保護者の同期ファイル形式](/schooldatasync/parent-contact-sync-file-format)」を参照してください。

- 学生は、 [課題設定](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)で教師が電子メールを無効にしない少なくとも 1 つのクラスに属しています。

- 電子メールには、前の週または今後の週の期日を持つ割り当てに関する情報が含まれます。

この機能の既定の設定は [ **オフ] です**。

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode はブロックベースのコーディング プラットフォームであり、コンピューター サイエンスをすべての学生に提供します。

MakeCode は、Microsoft の [使用条件](https://go.microsoft.com/fwlink/?LinkID=206977) と [プライバシー](https://go.microsoft.com/fwlink/?LinkId=521839) ポリシーの対象となる Microsoft 製品です。

この機能の既定の設定は [ **オフ] です**。

Teams で MakeCode の割り当てを有効にするには、**Teams 管理 センター** に移動し、[**割り当て]** セクションに移動し、[MakeCode] トグル オプションを **[オン] に** 切り替えます。 **[保存]** を選択します。 これらの設定を有効にするには、数時間待ちます。

この機能のしくみの詳細については、この [ビデオデモ](https://makecode.com/blog/teams/teams-assignments)をご覧ください。

[MakeCode の詳細については、こちらをご覧ください](https://aka.ms/makecode)。

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) は学術的整合性サービスです。 これは、独自の条件とプライバシー ポリシーの対象となるサード パーティのサービスです。 お客様は、第三者の製品およびサービスの使用について責任を負います。

この機能の既定の設定は [ **オフ] です**。

組織で Turnitin を有効にするには、Turnitin サブスクリプションが必要です。 次に、Turnitin 管理コンソールで次の情報を入力できます。

- **TurnitinApiKey**: これは、管理コンソールの [統合] の下にある 32 文字の GUID です。
- **TurnitinApiUrl**: これは Turnitin 管理コンソールの HTTPS URL です。

この情報を取得するのに役立つ手順を次に示します。

**TurnitinApiUrl** は、管理コンソールのホスト アドレスです。
例: `https://your-tenant-name.turnitin.com`

管理コンソールでは、統合と統合に関連付けられた API キーを作成できます。

サイド メニューから [ **統合** ] を選択し、[ **統合の追加** ] を選択し、統合に名前を付けます。

![新しい統合の追加を示すスクリーンショット。](./educationImages/Assignments_mopo_turnitin2.png)

プロンプトに従うと、 **TurnitinApiKey** が表示されます。
API キーをコピーし、Microsoft Teams 管理センターに貼り付けます。  これは、キーを表示できる唯一の時間です。

![API キーのコピーを示すスクリーンショット。](./educationImages/Assignments_mopo_turnitin3.png)

この設定の管理センターで **[保存** ] ボタンをクリックすると、これらの設定が有効になるまで数時間待ちます。

## <a name="assignments-data"></a>割り当てデータ

課題には、教師と学生の両方によって生成される情報が格納されます。 すべてのデータは、教師と、情報がクラスで意図されている特定の学生との間で共同共有されます。 このデータには、SharePoint と SharePoint の外部の 2 つのストアがあります。

>[!NOTE]
>読み取り進行状況などのファースト パーティの統合にも同じルールが適用されます。

### <a name="assignments-data-in-sharepoint-document-libraries"></a>SharePoint ドキュメント ライブラリの割り当てデータ

課題の提出に関連付けられた学生のファイルは、ドキュメント ライブラリ (Student *Work* という名前) に格納されます。 教師によって作成され、学生がアクセスできる課題に関連付けられたファイルは、対応するクラス チーム SharePoint サイトの別のドキュメント ライブラリ (クラス *ファイル*) に格納されます。 ファースト パーティの統合では、割り当てデータが同じ対応する Class Team SharePoint サイト (名前: *Assignments title + time stamp*) に格納される場合もあります。

#### <a name="files-associated-with-the-student"></a>学生に関連付けられているファイル

IT 管理者は、コンテンツ検索ツールを使用して、課題の提出や課題に関連するファイルに関連する学生ファイル (*学生の作業*、 *クラス ファイル*、またはその他のファースト パーティの統合ファイル) を検索できます。 たとえば、管理者は組織内のすべての SharePoint サイトを検索し、検索クエリで学生の名前とクラスまたは課題名を使用して、データ主体要求 (DSR) に関連するデータを検索できます。

#### <a name="files-associated-with-the-teacher"></a>教師に関連付けられているファイル

IT 管理者は、コンテンツ検索ツールを使用して、課題に関するクラス内の教師が学生に配布する課題とファイルに関連する教師ファイル (*学生の作業*、 *クラス* ファイル、またはその他のファースト パーティ統合ファイル) を検索できます。 たとえば、管理者は組織内のすべての SharePoint サイトを検索し、検索クエリで教師の名前とクラスまたは割り当て名を使用して、DSR に関連するデータを検索できます。

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>SharePoint ドキュメント ライブラリの外部での割り当てデータ

割り当てに関連する一部のデータは、クラス チームの SharePoint サイトに格納されていないため、コンテンツ検索では検出できません。 これには、次のものが含まれます。

- 学生の成績と教師からのフィードバック
- 各学生が課題のために提出したドキュメントの一覧
- 期限などの割り当ての詳細。
- リーディング プログレス パッセージや学生の発音データなどのファースト パーティ統合データ

この種類のデータの場合、教師などの IT 管理者またはデータ所有者は、DSR に関連するデータを見つけるために、クラス チームの割り当てに入る必要がある場合があります。 管理者は、所有者としてクラスに自分自身を追加し、そのクラス チームのすべての割り当てを表示できます。

>[!NOTE]
>学生がクラスの一部でなくなった場合、そのデータは *、登録されなくなった* としてもクラスに存在する可能性があります。 学生は、テナント管理者に、これまで参加していたクラスの一覧を提供する必要があります。

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>SharePoint ドキュメント ライブラリの外部で割り当てデータを一括エクスポートする

#### <a name="for-a-student"></a>学生の場合

1 人の学生のデータを一括エクスポートするには、自分が属するクラスから学生を削除する前 [に、スクリプトを実行](/microsoft-365/education/deploy/configure-assignments-for-teams) し、 を指定します ``userId``。 学生がサイトから削除された場合は、管理者がスクリプトを実行する前に学生をクラスに戻すか、管理者が学生がこれまで参加していた と を``classId``指定``userId``できます。

学生の提出に関するデータがエクスポートされます。

#### <a name="for-a-teacher"></a>教師の場合

一括エクスポート割り当てデータは学生と同じように機能しますが、教師がアクセスできるすべての提出がエクスポートされます。

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>SharePoint ドキュメント ライブラリの外部で割り当てデータを一括削除する

#### <a name="for-a-student"></a>学生の場合

1 人の学生のデータを一括削除するには、その学生が属しているクラスから学生を削除する前 [に、スクリプトを実行](/microsoft-365/education/deploy/configure-assignments-for-teams) し、 を指定します ``userId``。 学生がサイトから削除された場合は、管理者がスクリプトを実行する前に学生をクラスに戻すか、管理者が学生がこれまで参加していた と を``classId``指定``userId``できます。

を ``ClassId`` 指定すると、管理者は特定のクラスから学生に関する情報のみを削除できます。

#### <a name="for-a-teacher"></a>教師の場合

教師の課題のデータはクラス全体で共有されるため、一括削除オプションはありません。 代わりに、管理者はクラスに自分自身を追加し、アプリに移動して割り当てを削除できます。

詳細については、「 [Teams の割り当てを構成する](/microsoft-365/education/deploy/configure-assignments-for-teams)」を参照してください。

## <a name="removing-assignments-and-grades"></a>課題と成績の削除

また、Teams ポリシーを使用して、特定のユーザーまたはテナント全体の割り当てと成績を削除することもできます。

個々のユーザーの割り当てと成績を削除するには、**Teams 管理 センター** に移動し、**Teams アプリ>アクセス許可ポリシー** に移動して、新しいアプリアクセス許可ポリシー定義を作成します。  新しいポリシー定義を作成するときは、 **Microsoft アプリ** ポリシーを [特定のアプリをブロックする] に設定 _し、他のすべてのアプリを許可し_ 、ブロックされているアプリケーションの一覧に **割り当て** と **成績** を追加します。 新しいポリシー定義が保存されたら、適切なユーザーに割り当てます。

テナント全体の課題と成績を削除するには、**Teams 管理 センター** に移動し、[**アプリの管理] > [Teams アプリ**] に移動し、アプリケーションの一覧から **[課題** と **成績**] を検索して選択します。 アプリケーションの設定ページ内の状態設定を _[ブロック]_ に変更します。

## <a name="assignments-diagnostic-tool-for-users"></a>ユーザーの割り当て診断ツール

Microsoft サポートは、割り当て機能に関連する問題を調査するために、Microsoft エンジニアリング チームの診断データを収集するツールを作成しました。

このツールは、ユーザーが問題を発生させた任意の画面で、割り当ての内部でアクセスできます。

Teams で診断ツールをプルするには、次のことができます。

- **デスクトップと Web:**
  - Ctrl キーを押しながら/ を選択します
- **モバイル デバイスの場合:**
  - 2 本の指で画面をタッチし、指を 45 度回転させるか、または
  - 3 本指で 15 秒間画面をタップする

診断ツールが表示されると、Microsoft テクニカル サポートが必要とする可能性があるデータの一覧がユーザーに表示されます。

プルされるデータには、次のものが含まれます。

- グループ ID
- テナント ID
- セッション ID
- 割り当て ID
- 申請 ID
- ユーザー ID

このデータは Microsoft に自動的に送信されません。 ユーザーは、サポート チケットに関するデータをコピーして Microsoft サポート エージェントに貼り付ける必要があります。

ユーザーが診断ツールをプルして閉じると、データは送信されません。

データが Microsoft サポート エージェントに送信されると、組織の Microsoft 365 サービス契約の下でサポート データとして処理されます。

教師や学生と共有できるこの診断ツールの使用方法については、「 [診断データを取得して課題のトラブルシューティングを行](https://support.microsoft.com/topic/b40793f5-dbae-4c8a-841a-6baa7f232e2e)う」を参照してください。
