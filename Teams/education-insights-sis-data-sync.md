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
ms.openlocfilehash: 8f6d4a7dca340d297543abb3620a36cdd804ca9f
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196581"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>学生情報システム (SIS) データを Education Insights と同期する
より多くのデータが [Education Insights](class-insights.md) に提供されるほど、教師はより適切に学生をサポートでき、教育リーダーはより適切に教師をサポートできます。

組織レベルの Insights を提供するには、[学校データ同期 (SDS)](https://docs.microsoft.com/SchoolDataSync) を使用して学生情報システム (SIS) に接続する必要があります。これは、Insights が教育システムの階層構造を正しくマッピングできるようにするためです。 

クラスの教師としてクラス レベルの Insights を表示する場合は、この同期は *必要ありません*。これは、Teams のクラス構造とアクセス許可が使用されるためです。

## <a name="plan-your-sis-integration"></a>SIS の統合を計画する
SIS データは、教育システムの階層構造を提供し、どのユーザーがどこに割り当てられているかをマップします。

Insights は [SDS V2 ファイル形式](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format)を使用する場合に最適に機能しますが、機能が *制限* された [SDS V1 ファイル形式](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds)もサポートします。

### <a name="differences-between-sds-v1-and-v2-file-formats"></a>SDS V1 ファイル形式と SDS V2 ファイル形式の違い

| データの種類 |   V1 | V2 (新規のお客様におすすめ) |
|:--- |:--- |:--- |
| **ユーザー** | V1 ファイル形式には、**教師のみ** が含まれます。そのため、教育リーダーに対して組織レベルのアクセス許可を設定するには、該当者を検索し、それぞれのアクセス許可を手動で定義する必要があります。 | V2 ファイル形式には **すべての役割** が含まれます。そのため、役割ベースのアクセス許可を割り当てることができます。 |
| **組織** | V1 ファイル形式には、**学校のみ** が含まれます。したがって、1 つの集計レベル (すべての学校) のみが表示されます。 単純なリストを使用して特定の学校にズームインできますが、このリストには多数の学校が含まれている場合や、比較が難しいさまざまな種類の学校 (小学校から中学校、科学系から芸術系の学校など) が含まれている場合があります。<br/><br/> 階層が設定されている場合は、科学系や芸術系の学部など、意味のあるレベルを作成できます。| V2 ファイル形式には、総合大学、単科大学、学部、キャンパス、地域、プログラムなどを含む、**学区または教育機関の完全な階層** が含まれています。<br/><br/> 階層を使用すると、階層のレベルごとに関連する集計を確認したり、各レベルの組織単位をすばやく比較したり、特定のレベルに権限を割り当てたり、組織レベルごとに目標を設定したりできます。|

### <a name="type-of-data-required"></a>必要なデータの種類
次の表は、Insights を最大限に活用するために必要なデータの種類を示しています。

| データの種類 | 入力するデータの例|重要な理由|
|:--- |:--- |:--- |
| **ユーザー** |   役割 (学生など)<br/> [学年](#supported-grade-level-values) (10 など)<br/> 組織 (名前) | 各ユーザーがそれぞれの役割、学年、および組織に正しく割り当てられていれば、要約と集計に間違いが生じません。|
| **組織** | 組織の種類 (単科大学など) |   ここでは階層が重要です。 たとえば、学校がある地区に属し、その地区がある都道府県に属している場合があります。<br/> ある地区の教育リーダーがデータの表示を許可されている場合、その地区の学校のみが対象となります。|
| **クラス** | タイトル (コンピューター サイエンス 101 など) | このテーブルは、組織内で開講されているクラスの詳細を示します。 学生を適切なクラスに割り当てることができるように、このテーブルは正しくマッピングされている必要があります。 |
| **登録** | 役割 (学生など) | このテーブルは学生と教師向けのデータです。学生や教師がどのクラスに登録されているのかを知ることができます。 |

> [!NOTE]
> 展開プロセス中に、Teams のユーザーとクラスのプロビジョニングに SDS を使用するか、Insights にデータを提供するためだけに SDS を使用するかを決定できます。

## <a name="best-practices"></a>ベスト プラクティス
階層と、その階層内の全員が属する場所を正確にマッピングすることにより、Insights は、さまざまな種類の教育リーダーに対して、正確なデータと、より詳細かつ重要な分析情報を提供できます。

ここで入力するデータがより詳細であるほど、レポートとスポットライトの有用性と重要性が高まります。
ユーザーが Insights を最大限に活用できるように、SDS のスムーズな展開を確実にするためのいくつかのベスト プラクティスを次に示します。

### <a name="users"></a>ユーザー
*   提供するファイルに *すべてのユーザー* がリストされ、同期済みであることを確認します。 これには、対象となる組織単位のデータを確認する必要があるすべての学生とスタッフが含まれます。

    現在 SIS に教師のみがリストされている場合は、ファイルを SIS にアップロードしてデータを同期する前に、他のユーザーを手動で追加してください。

    一部の学生が含まれていない場合、Insights によって収集された統計は登録された学生のみのものであり、データと結論は誤解を招く可能性があります。
    
*   必ず *各ユーザーの姓と名を入力* してください。 入力しない場合、ユーザーはメール アドレスによって参照されます。これはレポートとスポットライト (学生のアクティビティやパフォーマンスに関する分析情報を含むカード) において、実用的なエクスペリエンスとは言えません。

*   *学年は 2 桁で入力する必要があります* (たとえば、学年が 7 の場合は「07」と入力します)。 詳しくは、[マッピング リスト](#supported-grade-level-values)を参照してください。 

*   学年でデータをフィルタ処理できるように、*すべての学生に学年を追加する* ことが重要です。    

*   *各ユーザーを関連する組織単位に割り当ててください*。 これにより、各組織単位の集計データに基づくスポットライトに誤解を招くデータが表示されなくなります。

    *   学生は、複数の組織単位に関連付けることができます。たとえば、特別なプログラムや 2 つの学部に登録されている学生などです。 このような場合、その学生のユーザー ファイルでは 2 行 (組織ごとに 1 行) に入力します。
    
    *   スタッフの組織単位に基づいて、関連するアクセス許可を定義できます。 必要なアクセス許可が与えられるように、スタッフが適切な組織単位レベルに関連付けられていることを確認してください。 たとえば、4 つの学校に割り当てられているカウンセラーは、それらの学校のすべてのクラスを表示する必要があります。校長は自分の学校のすべてのクラスを表示する必要があります。 
    
*   役割はきわめて重要です。 このリストは閉じられていますが、[こちらのリスト](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)の役割と、アップロードする各ユーザーの実際の役割を一致させるようにしてください。 それにより、役割ベースのアクセス許可を適切に割り当てることができます。 たとえば、すべての校長に対して自分の学校のクラスを表示するアクセス許可を、またはすべての教授に対して自分の学部を表示するアクセス許可を与えます。 

### <a name="organizations"></a>組織

* *自分の組織の実際の階層を反映するようにしてください*。 これは、ファイルを手動で追加することで実現できます。 この階層は SIS に反映されないこともあります。 その場合でも、階層のレベルごとに関連する集計を確認したり、特定のレベルにアクセス許可を割り当てたり、組織レベルで目標を設定したりする必要がある場合があります。 

* *組織ツリーの下位にあるすべての組織単位に、学生またはクラスが含まれている* ことを確認して、組織の学生データを集計します。 学生がツリーの末端の枝に含まれるようにすることをお勧めします。

> [!NOTE]
> SDS 展開の詳細については、「[SDS の計画](https://docs.microsoft.com/schooldatasync/planning-school-data-sync)」を参照してください。

## <a name="integrate-sis-using-sds"></a>SDS を使用して SIS を統合する

学校データ同期 (SDS) は Office 365 for Education で提供されます。 SDS は、教育機関の学生情報システム (SIS) からデータを読み取り、それを Teams と統合して、オンライン教室とユーザーの自動作成を可能にします。

また、SIS データを Insights と同期します。

### <a name="sync-with-insights"></a>Insights と同期する

まず、同期プロセスを開始するには、Insights トグルをオンにする必要があります。

* [**SDS ポータル**](https://sds.microsoft.com)で **[設定]** に移動し、下にスクロールして **[Collect data for Insights]** (Insights 用のデータを収集する) が有効になっていることを確認します (既定では *オン* になっています)。

* 下にスクロールして、次のスイッチ **[Sync organizational data from SDS (preview)]** (SDS の組織データを同期する (プレビュー)) をオンにします。

[設定] ページに *[Sync organizational data from SDS (preview)]* オプションが表示されない場合は、[サインアップ ページ](https://aka.ms/insights/join) に移動して自分の情報を入力すると、チーム メンバーから連絡があります。

:::image type="content" source="media/insights-sds-settings.png" alt-text="Insights との同期トグル":::

### <a name="deploy-sds"></a>SDS を展開する
**すでに SDS を使用している場合は**、「[ベスト プラクティス](#best-practices)」に従うことをお勧めします。 

現在のプロファイルを Insights と同期するには、**同期プロファイル** に移動し、**[編集]** をクリックして **[Insights に同期]** を選択します。 初回の同期においては、SIS からデータが更新された後にレポートを利用できるようにするために、24 時間待機することが推奨されます。  

:::image type="content" source="media/insights-sds-profile-sync.png" alt-text="プロファイルを Insights トグルと同期する":::

**SDS を使用していない場合は**、[SDS を展開する](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync)必要があります。

展開プロセス中に、Teams のユーザーとクラスのプロビジョニングに SDS を使用するか、Insights にデータを提供するためだけに SDS を使用するかを決定できます。

> [!NOTE]
> 年央で、すでに手動でチームを作成している場合は、Insights にデータを提供するためだけに SDS を使用するとしておき、来年は Teams のユーザーとクラスのプロビジョニングにも SDS を使用することを検討してください。

### <a name="verify-the-sync-process"></a>同期プロセスを確認する
[設定] ページの [SDS から組織データを同期する (プレビュー)] の横に新しい [状態] 領域が表示されます。
 
*   状態が "**処理中**" の場合は、SDS プロファイルの展開後、最大で 24 時間お待ちください。

*   状態が "**完了**" の場合は、組織レベルで Insights を表示することができ、次のステップに進むことができます。

*   状態が "**完了 (エラーあり)**"、"**完了 (警告あり)**"、または "**中止**" の場合は、最新の同期のエラーと警告を含むログ ファイルをダウンロードし、それらのエラーを修正できるかどうかを確認します。 

> [!IMPORTANT]
> 問題が発生した場合は、[カスタマー サポート](https://aka.ms/edusupport)にお問い合わせください。

## <a name="supported-grade-level-values"></a>サポートされている学年の値

SDS ファイルでは、学年は列挙値として定義されています。つまり、CSV ファイル内で指定されている値のセットのみを入力できます。 指定されている値以外の値を入力すると、同期処理中にエラーとなります。

> [!NOTE]
> *学年は 2 桁で入力する必要があります* (たとえば、Year 7 の場合は「07」と入力します)。

以下のセクションでは、users ファイルでサポートされている値を定義します。

### <a name="united-states--worldwide-grade-levels"></a>米国 / 世界的に用いられる学年
|ファイル内の値 (Grade 列) | Insights のラベル|
|:---|:---| 
|IT|Infant (保育園)|
|PR|Pre-school (保育園)|
|PK|Pre-kindergarten (保育園)|
|TK|Transitional Kindergarten (幼稚園 - 年少)|
|KG|Kindergarten (幼稚園)|
|01|First grade (1 年)|
|02|Second grade (2 年)|
|03|Third grade (3 年)|
|04|Fourth Grade (4 年)|
|05|Fifth grade (5 年)|
|06|Sixth grade (6 年)|
|07|Seventh grade (7 年)|
|08|Eighth grade (8 年)|
|09|Ninth grade (9 年)|
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
|Other|Other (その他)|

### <a name="united-kingdom-year-groups"></a>英国の学年グループ
|ファイル内の値 (Grade 列) | Insights のラベル|
|:---|:---| 
|IT|Nursery (保育園)|
|PR|Pre-school (保育園)|
|PK|Reception (幼稚園)|
|01|Year 1 (1 年)|
|02|Year 2 (2 年)|
|03|Year 3 (3 年)|
|04|Year 4 (4 年)|
|05|Year 5 (5 年)|
|06|Year 6 (6 年)|
|07|Year 7 (7 年)|
|08|Year 8 (8 年)|
|09|Year 9 (9 年)|
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
