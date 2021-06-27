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
ms.openlocfilehash: 5d5ba5c2c5179d5c333472450fd9b2e9c270a4e9
ms.sourcegitcommit: 7579dda8018691eb1a724cb0311b53333dc3ae5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "53142843"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>学生情報システム (SIS) データを Education Insights と同期する
より多くのデータが [Education Insights](class-insights.md) に提供されるほど、教師はより適切に学生をサポートでき、教育リーダーはより適切に教師をサポートできます。

組織レベルの Insights を提供するには、[学校データ同期 (SDS)](/SchoolDataSync) を使用して学生情報システム (SIS) に接続する必要があります。これは、Insights が教育システムの階層構造を正しくマッピングできるようにするためです。 

クラスの教師としてクラス レベルの Insights を表示する場合は、この同期は *必要ありません*。これは、Teams のクラス構造とアクセス許可が使用されるためです。

## <a name="plan-your-school-data-sync-integration"></a>School Data Sync の統合を計画する
Microsoft School Data Sync (a.k.a SDS) は、学生情報システム (a.k.a SIS) のデータと教育システムの階層構造を提供し、どのユーザーがどこに割り当てられているかをマッピングするとともに、学生や組織の階層に関する追加データを提供します。

Insights は [SDS V2.1.ファイル形式](/schooldatasync/sds-v2.1-csv-file-format)以上を使用する場合にベストに機能しますが、機能が制限された [SDS V2 ファイル形式](/schooldatasync/sds-v2-csv-file-format) および  [SDS V1 ファイル形式](/schooldatasync/school-data-sync-format-csv-files-for-sds) *もサポートします*。


### <a name="differences-between-sds-v1-and-v2-file-formats"></a>SDS V1 ファイル形式と SDS V2 ファイル形式の違い

| データの種類 | V1 | V2 および V2.1 |
|:--- |:--- |:--- |
| **ユーザー** |"教師" ロールのみをサポートするため、教育リーダーの組織レベルのアクセス許可を手動で設定する必要があります|ロールベースのアクセス許可を設定できるように、複数のロールをサポートします|
| **組織** | 'schools'、集計レベルのみをサポートします。<br><br>その結果、複数の集計レベルが提供されず、異なる種類の学校 (小学校と中学校、サイエンス スクール、アート スクールなど) を比較する機能が制限されます。|学区/機関、大学、カレッジ、学部、キャンパス、地域、プログラムなどの多層階層をサポートします。<br><br>複数の集計レベルを使用でき、各レベルの組織単位間の比較、特定のレベルへのアクセス許可の割り当て、組織レベル別の目標の設定などを簡単に行うことができます。|
| **追加のオプション情報** |なし|**V2.1 ファイル形式のみ**<br><br>*学期* - セッションの時間枠 (半期、学年など)<br><br>人口統計と学生のフラグ* - 人種、民族、性別などのデータだけでなく、特別なプログラム (IEP、504)|

> [!NOTE]
> 2021 年 7 月 15 日以降、ファイル形式 v2 をオンボードすることができなくなり、代わりに v2.1 形式を使用する必要があります。今後のアップグレードや新しい機能はすべて v2.1 形式で行われ、ファイル形式 v1 との完全な下位互換性があります。

### <a name="best-practices"></a>ベスト プラクティス

階層と、その階層内の全員が属する場所を正確にマッピングすることにより、Insights は、さまざまな種類の教育リーダーに対して、正確なデータと、より詳細かつ重要な分析情報を提供できます。

入力するデータがより詳細であるほど、レポートとスポットライトの有用性と重要性が高まります。

#### <a name="file-format-version-to-use-adn-data-to-sync"></a>使用するファイル形式のバージョンと同期するデータ
*   ファイル形式 V2.1 を使用し、[ここ](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv)に記載してある Education Insights が使用するオプションデータを同期します。

#### <a name="users-and-roles"></a>ユーザーおよび役割
*   提供するファイルに **すべてのユーザー** がリストされ、同期済みであることを確認します。 これには、対象となる組織単位のデータを確認する必要があるすべての学生とスタッフが含まれます。
*   現在 SIS に教師のみがリストされている場合は、ファイルを SDS にアップロードしてデータを同期する前に、他のユーザーを手動で追加してください。 Insights によって収集された統計は登録された学生のみからであり、一部の学生が含まれず、データと結論は誤解を招く可能性があります。
    
*   プロビジョニングにも SDS を使用する場合は、**各ユーザーの姓と名を提供** してください。 それ以外の場合、学生は自分のメール アドレスで参照されるため、最適ではないエクスペリエンスが得られます。

*   級/学年は、この[マッピング リスト](#supported-grade-level-values)に基づいている必要があります。 

*   確実に **すべての学生に級/学年レベルを追加** してください。    

*   確実に **各ユーザーを関連する組織単位に割り当ててください**。

    *   学生は、複数の組織単位に関連付けることができます。たとえば、特別なプログラムや 2 つの学部に登録されている学生などです。 学生が複数の組織単位を持っている場合は、その学生のユーザー　ファイルにそれぞれの行を指定します。
    
    *   IT 管理者は、スタッフの組織単位に基づいてアクセス許可を付与することができます。 必要なアクセス許可が与えられるように、**スタッフ メンバーが適切な組織単位レベルに関連付けられていることを確認してください**。 たとえば、4 つの学校に割り当てられているカウンセラーは、それらの学校のすべての学年を表示する必要があります。校長は自分の学校のすべてのクラスを表示する必要があります。 
    
*   **役割はきわめて重要です**。 このリストは閉じられていますが、[こちらのリスト](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)の役割と、アップロードする各ユーザーの実際の役割を一致させるようにしてください。 これにより、役割ベースのアクセス許可を適切に割り当てることができます。 たとえば、すべての校長に対して自分の学校のクラスを表示するアクセス許可を、またはすべての教授に対して自分の学部を表示するアクセス許可を与えます。 

#### <a name="organizations"></a>組織

* **自分の組織の実際の完全な階層を反映するようにしてください**。 場合によっては、この階層は SIS に反映されません。その場合は、CSV ファイルの同期前に手動で追加する必要があります。

* **組織ツリーの下にあるすべての組織単位に、学生またはクラスが含まれている** ことを確認してください。 学生がツリーの末端の枝に含まれるようにすることをお勧めします。

> [!NOTE]
> SDS 展開の詳細については、「[SDS の計画](/schooldatasync/planning-school-data-sync)」を参照してください。

## <a name="integrate-sis-data-using-sds"></a>SDS を使用して SIS データを統合する

School Data Sync (SDS) には、Office 365 for Education が提供されており、教育機関の学生情報システム (SIS) からデータを読み取り、それを Teams などの Microsoft アプリケーションと統合して、オンライン教室とユーザーの自動作成を可能にします。

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

