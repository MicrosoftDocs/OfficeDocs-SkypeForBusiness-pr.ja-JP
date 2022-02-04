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
description: Microsoft Teams 管理センターで課題を管理する方法についてMicrosoft Teams for Education。
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88414131b5ba8fee750efef8d0b6f6f5313e13fd
ms.sourcegitcommit: 1129841e68e927fe7cc31de3ad63a3e9247253cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2022
ms.locfileid: "62363143"
---
# <a name="assignments-in-teams-for-education"></a>教育機関向けの Teams の課題 

教師は、学生にタスク、Microsoft Teams for Education、またはテストを割り当て可能な課題と成績機能を提供します。 教師は、課題のタイムラインの管理、手順の管理、リソースの追加、ルーブリックを使用した成績の取得など、その他の操作を行えます。 また、[成績] タブでクラスと個々の学生の進捗状況を追跡することもできます。

[課題と成績の詳細については、Microsoft Teams for Education](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)。

> [!Note]
> さまざまなプラットフォームでのTeamsの詳細については、「プラットフォーム別のTeams[を参照してください](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>管理センターでの割りMicrosoft Teams統合

管理センターの管理者設定Microsoft Teams、組織内の教師とその学生の機能を有効またはオフにできます。 課題に関連する設定を次に示します。

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>週 1 回の保護者のメール ダイジェスト

保護者のメールは、週末ごとに保護者または保護者に送信されます。 メールには、前の週と来週の課題に関する情報が含まれている。 親と保護者の同期は、次のコマンドを使用[学校データ同期](/schooldatasync/parent-contact-sync)。

1. SDS で親と保護者の同期を使用して親の連絡先情報をインポートします。 親と保護者の同期を有効にする方法については、「親と保護者の同期を有効 [にする」を参照してください](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)。

2. 設定が既定でオフになっているMicrosoft Teams管理センターで [保護者の設定] をオンにします。 これにより、教師は週刊ダイジェストを送信できます。

   > [!NOTE]
   > 教師は、自分の個人クラス チーム内の設定を選択解除することで、ダイジェストをオプトアウトできます ([割り当て] 設定 >**親/** 保護者の電子メール)。

保護者がメールを受け取るのを確認するには、次の 3 つの項目が true である必要があります。

- SDS で学生のプロフィールに添付され、親または保護者としてタグ付 _けされた__メール アドレス。_ 詳細については、「親と保護者 [の同期ファイル形式」を参照してください](/schooldatasync/parent-contact-sync-file-format)。

- 学生は、課題設定で教師がメールを無効にしていない少なくとも 1 つのクラス [に属しています](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)。

- メールには、前の週または来週の期限がある割り当てに関する情報が含まれる。

この機能の既定の設定は - **オフです**。

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode は、すべての学生にコンピューター サイエンスを生き生きとさせるブロックベースのコーディング プラットフォームです。

MakeCode は、Microsoft の使用条件とプライバシー ポリシーの [対象となる Microsoft](https://go.microsoft.com/fwlink/?LinkID=206977) [製品](https://go.microsoft.com/fwlink/?LinkId=521839) です。

この機能の既定の設定は - **オフです**。

Teams で MakeCode の割り当てを有効にするには、**Teams 管理** センターに移動し、[割り当て] セクションに **移動** し、[MakeCode] トグル オプションを [オン **] にします。** **[保存]** をクリックします。 これらの設定を有効にするために数時間を許可します。

この機能のしくみの詳細については、このビデオデモをご [覧ください](https://makecode.com/blog/teams/teams-assignments)。

[MakeCode の詳細については、次を参照してください](https://aka.ms/makecode)。

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin は](https://www.turnitin.com/) 教育機関向け整合性サービスです。 これは、独自の条項とプライバシー ポリシーの対象となるサード パーティのサービスです。 お客様は、サード パーティの製品およびサービスを使用する責任を負います。

この機能の既定の設定は - **オフ** です。

組織で Turnitin を有効にするには、Turnitin サブスクリプションが必要です。 次に、Turnitin 管理コンソールで確認できる次の情報を入力できます。

- **TurnitinApiKey**: 管理コンソールの [統合] にある 32 文字の GUID です。
- **TurnitinApiUrl**: これは、Turnitin 管理コンソールの HTTPS URL です。

この情報の取得に役立つ手順を次に示します。

**TurnitinApiUrl は**、管理コンソールのホスト アドレスです。
例: `https://your-tenant-name.turnitin.com`

管理コンソールでは、統合と、統合に関連付けられている API キーを作成できます。

サイド **メニューから [統合** ] を選択し、[統合の追加] **を選択** し、統合に名前を付きます。

![新しい統合の追加を示すスクリーンショット。](./educationImages/Assignments_mopo_turnitin2.png)

**プロンプトに従った後、TurnitinApiKey** が表示されます。
API キーをコピーし、管理センターのMicrosoft Teamsします。  キーを表示できるのは今回のみです。

![API キーのコピーを示すスクリーンショット。](./educationImages/Assignments_mopo_turnitin3.png)

この設定 **に対して** 管理センターの [保存] ボタンをクリックすると、これらの設定が有効になります。

## <a name="assignments-data"></a>割り当てデータ

課題には、教師と学生の両方によって生成される情報が格納されます。 すべてのデータは、教師と、情報がクラスで意図されている特定の学生の間で共同共有されます。 この 2 つのストアは、SharePointと外部の 2 SharePoint。

>[!NOTE]
>同じルールは、閲覧の進行状況などのファースト パーティの統合にも適用されます。

### <a name="assignments-data-in-sharepoint-document-libraries"></a>ドキュメント ライブラリ内SharePointデータを割り当て

課題提出に関連付けられている学生のファイルは、ドキュメント ライブラリ (名前: *Student Work) に保存されます*。 教師によって作成され、学生がアクセスできる課題に関連付けられているファイルは、対応するクラス チームサイト内の別のドキュメント ライブラリ (クラス *ファイル) SharePoint* されます。 また、ファースト パーティの統合では、同じ対応するクラス チーム サイト ("課題タイトル + タイム スタンプSharePoint) に課題データを *格納できます*。

#### <a name="files-associated-with-the-student"></a>学生に関連付けられているファイル

IT 管理者は、コンテンツ検索ツールを使用して、課題の提出と課題に関連する *ファイルに関連* する学生ファイル (学生の作業、クラス ファイル、または他の第 1 者統合ファイル) を検索できます。 たとえば、管理者は組織内のすべての SharePoint サイトを検索し、検索クエリで学生の名前とクラス名または課題名を使用して、データサブジェクト要求 (DSR) に関連するデータを検索できます。

#### <a name="files-associated-with-the-teacher"></a>教師に関連付けられているファイル

IT 管理者は、コンテンツ検索ツールを使用して、課題に関連する教師 *ファイル (学生* の作業ファイル、クラス ファイル、または他の 1st-party 統合ファイル) と、課題のクラス内の教師によって学生に配布されたファイルを検索できます。  たとえば、管理者は組織内のすべての SharePoint サイトを検索し、検索クエリで教師の名前とクラス名または課題名を使用して、DSR に関連するデータを検索できます。

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>ドキュメント ライブラリ以外のデータSharePoint割り当て

課題に関連する一部のデータは、クラス チーム SharePoint サイトに保存されません。つまり、コンテンツ検索では検出できません。 これには、次の内容が含まれます。

- 教師からの学生の成績とフィードバック
- 各学生が課題のために提出したドキュメントの一覧
- 割り当ての詳細 (期限など)
- 閲覧の進行状況の一節や学生の発音データのようなファースト パーティ統合データ

この種類のデータでは、教師などの IT 管理者またはデータ所有者が、DSR に関連するデータを見つけるためにクラス チームの課題に入る必要がある場合があります。 管理者は自分自身をクラスの所有者として追加し、そのクラス チームのすべての割り当てを表示できます。

>[!NOTE]
>学生がクラスに含めなくなった場合、その学生のデータは、登録されなくなったクラス *に引き続き存在する可能性があります*。 学生は、これまで参加していたクラスの一覧をテナント管理者に提供する必要があります。

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>ドキュメント ライブラリ以外の割り当てSharePoint一括エクスポート

#### <a name="for-a-student"></a>学生の場合

1 人の学生のデータを一括エクスポートするには、その学生が参加しているクラスから学生を削除する前に、スクリプトを [実行](/microsoft-365/education/deploy/configure-assignments-for-teams) し、 を指定します ``userId``。 学生が``userId````classId``サイトから削除された場合は、管理者がスクリプトを実行する前に学生をクラスに追加し戻すか、管理者が 学生が参加した と を指定できます。

学生の提出に関するデータがエクスポートされます。

#### <a name="for-a-teacher"></a>教師向け

一括エクスポートの課題データは学生と同じように機能しますが、教師がアクセスできるすべての提出はエクスポートされます。

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>ドキュメント ライブラリの外部にある割り当SharePoint一括削除

#### <a name="for-a-student"></a>学生の場合

1 人の学生のデータを一括削除するには、その学生が参加しているクラスから学生を削除する前に、スクリプトを [実行](/microsoft-365/education/deploy/configure-assignments-for-teams) し、 を指定します ``userId``。 学生が``userId````classId``サイトから削除された場合は、管理者がスクリプトを実行する前に学生をクラスに追加し戻すか、管理者が 学生が参加した と を指定できます。

を指定 ``ClassId`` すると、管理者は特定のクラスから学生に関する情報のみを削除できます。

#### <a name="for-a-teacher"></a>教師向け

教師の課題のデータはクラス全体で共有されるので、一括削除オプションはありません。 代わりに、管理者は自分自身をクラスに追加し、アプリに移動して、割り当てを削除できます。

詳細については、「割り当ての構成 [」を参照Teams](/microsoft-365/education/deploy/configure-assignments-for-teams)。

## <a name="removing-assignments-and-grades"></a>課題と成績の削除

特定のユーザーまたはテナントTeams割り当てと成績を削除するには、このポリシーを使用できます。

個々のユーザーの課題と成績を削除するには、**Teams** 管理センターに移動し、**Teams アプリ >** アクセス許可ポリシーに移動して、新しいアプリのアクセス許可ポリシー定義を作成します。  新しいポリシー定義を作成するときに、[**Microsoft アプリ**] ポリシーを  [特定のアプリをブロック] に設定し、他のすべてのアプリを許可し、ブロックされているアプリケーションの一覧に割り当てを追加します。 新しいポリシー定義を保存したら、適切なユーザーに割り当てる必要があります。

テナント全体の課題と成績を削除するには、[**Teams** 管理センター] に移動し、[Teams アプリ] **> [** アプリの管理] に移動し、アプリケーションの一覧から [割り当て] を検索して選択します。 [アプリケーションの割り当て設定] ページの状態設定を [ブロック] _に変更します_。
