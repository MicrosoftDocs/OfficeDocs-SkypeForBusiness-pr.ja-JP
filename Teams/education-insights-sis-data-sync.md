---
title: 学生情報システム (SIS) データを Education Insights と同期する
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 学生情報システム (SIS) データを Microsoft Teams の Education Insights と同期します。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b0d9ae3788be09e4a66724e6122791a91b6879f
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997736"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>学生情報システム (SIS) データを Education Insights と同期する
より多くのデータが [Education Insights](class-insights.md) に提供されるほど、教師はより適切に学生をサポートでき、教育リーダーはより適切に教師をサポートできます。

組織レベルの Insights を提供するには、[学校データ同期 (SDS)](/SchoolDataSync) を使用して学生情報システム (SIS) に接続する必要があります。これは、Insights が教育システムの階層構造を正しくマッピングできるようにするためです。 

クラスの教師としてクラス レベルの Insights を表示する場合は、この同期は *必要ありません*。これは、Teams のクラス構造とアクセス許可が使用されるためです。

## <a name="plan-your-school-data-sync-integration"></a>School Data Sync の統合を計画する
Microsoft School Data Sync (a.k.a SDS) は、学生情報システム (a.k.a SIS) のデータと教育システムの階層構造を提供し、どのユーザーがどこに割り当てられているかをマッピングするとともに、学生や組織の階層に関する追加データを提供します。

Insights は [SDS V2 ファイル形式](/schooldatasync/sds-v2-csv-file-format)以上を使用する場合に最適に機能しますが、*機能が制限された* [SDS V1 ファイル形式](/schooldatasync/school-data-sync-format-csv-files-for-sds)もサポートします。


### <a name="differences-between-sds-v1-and-v2-file-formats"></a>SDS V1 ファイル形式と SDS V2 ファイル形式の違い

分析情報を最大限に活用するには、ファイル フォーマット v2 または v2.1 を使用することをお勧めします (近日公開予定)。

| データの種類 | V1 | V2 |
|:--- |:--- |:--- |
| **ユーザー** | V1 ファイル形式には、**教師のみ** が含まれます。そのため、教育リーダーに対して組織レベルのアクセス許可を設定するには、それぞれのアクセス許可を手動で定義する必要があります。 | V2 ファイル形式には **すべての役割** が含まれます。そのため、役割ベースのアクセス許可を割り当てることができます。 |
| **組織** | V1 ファイル形式には、**学校のみ** が含まれます。したがって、1 つの集計レベル (すべての学校) のみが表示されます。 単純なリストを使用して特定の学校にズームインできますが、このリストには多数の学校が含まれている場合や、比較が難しいさまざまな種類の学校 (小学校から中学校、科学系から芸術系の学校など) が含まれている場合があります。<br/><br/> 階層が設定されている場合は、科学系や芸術系の学部など、意味のあるレベルを作成できます。| V2 ファイル形式には、総合大学、単科大学、学部、キャンパス、地域、プログラムなどを含む、**学区または教育機関の完全な階層** が含まれています。<br/><br/> 階層を使用すると、階層のレベルごとに関連する集計を確認したり、各レベルの組織単位をすばやく比較したり、特定のレベルに権限を割り当てたり、組織レベルごとに目標を設定したりできます。|

> [!NOTE]
> 2021 年 7 月 15 日以降、ファイル形式 v2 をオンボードすることができなくなり、代わりに v2.1 形式を使用する必要があります。今後のアップグレードや新しい機能はすべて v2.1 形式で行われ、ファイル形式 v1 との完全な下位互換性があります。

## <a name="best-practices"></a>ベスト プラクティス
階層と、その階層内の全員が属する場所を正確にマッピングすることにより、Insights は、さまざまな種類の教育リーダーに対して、正確なデータと、より詳細かつ重要な分析情報を提供できます。

入力するデータがより詳細であるほど、レポートとスポットライトの有用性と重要性が高まります。

ユーザーが Insights を最大限に活用できるように、SDS のスムーズな展開を確実にするためのいくつかのベスト プラクティスを次に示します。

### <a name="file-format-version-to-ue"></a>ファイル形式バージョンを ue に
*   ファイル形式 V2.1 (近日公開予定) を使用し、Education Insights が使用するオプションデータを同期します

### <a name="users-and-roles"></a>ユーザーおよび役割
*   提供するファイルに **すべてのユーザー** がリストされ、同期済みであることを確認します。 これには、対象となる組織単位のデータを確認する必要があるすべての学生とスタッフが含まれます。
    現在 SIS に教師のみがリストされている場合は、ファイルを SDS にアップロードしてデータを同期する前に、他のユーザーを手動で追加してください。
    Insights によって収集された統計は登録された学生のみのものであり、一部の学生が含まれず、データと結論は誤解を招く可能性があります。
    
*   必ず **各ユーザーの姓と名を入力** してください。 そうでない場合、ユーザーはメール アドレスによって参照されます。これはレポートとスポットライト (学生のアクティビティやパフォーマンスに関する分析情報を含むカード) において、最適化されたエクスペリエンスとは言えません。

*   学年/学年は、この[マッピング リスト](#supported-grade-level-values)に基づいている必要があります。 

*   アクティビティ データを集計し、それによってフィルター処理できるように、すべての学生に **年/学年を追加する** ことが重要です。    

*   **各ユーザーを関連する組織単位に割り当ててください**。 そうすることで、Education Insights スポットライトに誤解を招くようなデータが表示されることはありません。

    *   学生は、複数の組織単位に関連付けることができます。たとえば、特別なプログラムや 2 つの学部に登録されている学生などです。 学生が複数の組織単位を持っている場合は、その学生のユーザー　ファイルにそれぞれの行を指定します。
    
    *   IT 管理者は、スタッフの組織単位に基づいてアクセス許可を付与することができます。 必要なアクセス許可が与えられるように、**スタッフ メンバーが適切な組織単位レベルに関連付けられていることを確認してください**。 たとえば、4 つの学校に割り当てられているカウンセラーは、それらの学校のすべての学年を表示する必要があります。校長は自分の学校のすべてのクラスを表示する必要があります。 
    
*   **役割はきわめて重要です**。 このリストは閉じられていますが、[こちらのリスト](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)の役割と、アップロードする各ユーザーの実際の役割を一致させるようにしてください。 これにより、役割ベースのアクセス許可を適切に割り当てることができます。 たとえば、すべての校長に対して自分の学校のクラスを表示するアクセス許可を、またはすべての教授に対して自分の学部を表示するアクセス許可を与えます。 

### <a name="organizations"></a>組織

* **自分の組織の実際の完全な階層を反映するようにしてください**。 これは、ファイルを手動で追加することで実現できます。 この階層は SIS に反映されないこともあります。 その場合でも、階層のレベルごとに関連する集計を確認したり、特定のレベルにアクセス許可を割り当てたり、組織レベルで目標を設定したりする必要がある場合があります。 

* **組織ツリーの下位にあるすべての組織単位に、学生またはクラスが含まれている** ことを確認して、組織の学生データを集計します。 学生がツリーの末端の枝に含まれるようにすることをお勧めします。

> [!NOTE]
> SDS 展開の詳細については、「[SDS の計画](/schooldatasync/planning-school-data-sync)」を参照してください。

## <a name="integrate-sis-data-using-sds"></a>SDS を使用して SIS データを統合する

学校データ同期 (SDS) は Office 365 for Education で提供されます。 SDS は、教育機関の学生情報システム (SIS) からデータを読み取り、それを Teams などの Microsoft アプリケーションと統合して、オンライン教室とユーザーの自動作成を可能にします。

また、SIS データを Insights と同期します。

IT 管理者としては、SDS をプロビジョニングのみ、Insights のみ、またはその両方に使用することができます。

SIS の情報を Educations Insights と同期するには、[Insights 用 SDS の展開方法](/schooldatasync/how-to-deploy-sds-for-insights)の手順に従ってください。

### <a name="deploy-sds"></a>SDS を展開する
**すでに SDS を使用している場合は**、「[ベスト プラクティス](#best-practices)」に従うことをお勧めします。 

**SDS を使用していない場合は**、[SDS を展開する](/schooldatasync/deploying-school-data-sync)必要があります。

展開プロセス中に、Teams のユーザーとクラスのプロビジョニングに SDS を使用するか、Insights にもユーザーと組織の階層を提供するためにのみ使用するかを決めることができます。

> [!NOTE]
> 年央で、すでに手動でチームを作成している場合は、Insights にユーザーと組織階層のデータを提供するためだけに SDS を使用するとしておき、来年は Teams のユーザーとクラスのプロビジョニングにも SDS を使用することを検討してください。

### <a name="verify-the-sync-process"></a>同期プロセスを確認する
同期状態の進捗状況を確認するには、[Insights データの正常性と監視向け SDS](/schooldatasync/sds-for-insights-data-health-and-monitoring) の手順に従ってください。

> [!IMPORTANT]
> 問題が発生した場合は、[カスタマー サポート](https://aka.ms/edusupport)にお問い合わせください。

## <a name="supported-grade-level-values"></a>サポートされている学年の値

SDS ファイルでは、学年は列挙値として定義されています。つまり、CSV ファイル内で指定されている値のセットのみを入力できます。 指定されている値以外の値を入力すると、同期処理中にエラーとなります。

以下のセクションでは、users ファイルでサポートされている値を定義します。

### <a name="united-states--worldwide-grade-levels"></a>米国 / 世界的に用いられる学年
|ファイル内の値 (Grade 列) | Insights のラベル|
|:---|:---| 
|IT|Infant (保育園)|
|PR|Pre-school (保育園)|
|PK|Pre-kindergarten (保育園)|
|TK|Transitional Kindergarten (幼稚園 - 年少)|
|KG|Kindergarten (幼稚園)|
|01 または 1|First grade (1 年)|
|02 または 2|Second grade (2 年)|
|03 または 3|Third grade (3 年)|
|04 または 4|Fourth Grade (4 年)|
|05 または 5|Fifth grade (5 年)|
|06 または 6|Sixth grade (6 年)|
|07 または 7|Seventh grade (7 年)|
|08 または 8|Eighth grade (8 年)|
|09 または 9|Ninth grade (9 年)|
|10|Tenth grade (10 年)|
|11|Eleventh grade (11 年)|
|12|Twelfth grade (12 年)|
|PS|Postsecondary (高等教育)|
|PS1|Postsecondary freshman (大学 1 年)|
|PS2|Postsecondary sophomore (大学 2 年)|
|PS3|Postsecondary junior (大学 3 年)|
|PS4|Postsecondary senior (大学 4 年)|
|undergraduate|Undergraduate (大学)|
|graduate|Graduate (大学院)|
|postgraduate|Postgraduate (研究科)|
|alumni|Alumni (卒業生)|
|adultEducation|Adult Education (社会人教育)|
|UG|Ungraded (特殊教育)|
|Other (その他)|Other (その他)|

### <a name="united-kingdom-year-groups"></a>英国の学年グループ
|ファイル内の値 (Grade 列) | Insights のラベル|
|:---|:---| 
|IT|Nursery (保育園)|
|PR|Pre-school (保育園)|
|PK|Reception (幼稚園)|
|01 または 1|Year 1 (1 年)|
|02 または 2|Year 2 (2 年)|
|03 または 3|Year 3 (3 年)|
|04 または 4|Year 4 (4 年)|
|05 または 5|Year 5 (5 年)|
|06 または 6|Year 6 (6 年)|
|07 または 7|Year 7 (7 年)|
|08 または 8|Year 8 (8 年)|
|09 または 9|Year 9 (9 年)|
|10|Year 10 (10 年)|
|11|Year 11 (11 年)|
|12|Year 12 (12 年)|
|13|Year 13 (13 年)|
|PS|Postsecondary (高等教育)|
|PS1|Postsecondary Year 1 (大学 1 年)|
|PS2|Postsecondary Year 2 (大学 2 年)|
|PS3|Postsecondary Year 3 (大学 3 年)|
|PS4|Postsecondary Year 4 (大学 4 年)|
|undergraduate|Undergraduate (大学)|
|graduate|Graduate (大学院)|
|postgraduate|Postgraduate (研究科)|
|alumni|Alumni (卒業生)|
|adultEducation|Adult Education (社会人教育)|
|UG|Ungraded (特殊教育)|
|Other (その他)|Other (その他)|

