---
title: Teams での割り当て
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams for Education の管理センターで課題Teamsする方法について学習します。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 410f5d32dd8af4775639a080725cd5680b6a70c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121375"
---
# <a name="assignments-in-teams-for-education"></a>教育機関向けの Teams の課題 

Teams for Education の課題と成績の機能を使用すると、教師は学生にタスク、作業、またはテストを割り当てできます。 教師は、課題のタイムラインの管理、手順の管理、リソースの追加、ルーブリックを使用した成績の取得など、その他の操作を行えます。 また、[成績] タブでクラスと個々の学生の進捗状況を追跡することもできます。

[「Teams for Education の課題と成績」を参照してください](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)。

> [!Note]
> さまざまなプラットフォームでの Teamsの割り当ての詳細については、プラットフォーム別のTeams[を参照してください](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>管理センターでの割りMicrosoft Teams統合

管理センターの管理者設定Microsoft Teams、組織内の教師とその学生の機能を有効またはオフにできます。 課題に関連する設定を次に示します。

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>週 1 回の保護者のメール ダイジェスト


保護者のメールは、週末ごとに保護者または保護者に送信されます。 メールには、前の週と今後の週の課題に関する情報が含まれている。 親と保護者の同期は、 を使用[して学校データ同期。](/schooldatasync/parent-contact-sync)

1. SDS で親と保護者の同期を使用して親の連絡先情報をインポートします。 親と保護者の同期を有効にする方法については、「親と保護者の同期を有効 [にする」を参照してください](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)。

2. 設定が既定でオフになっているMicrosoft Teams管理センターで [保護者の設定] をオンにします。 これにより、教師は週刊ダイジェストを送信できます。

   > [!NOTE]
   > 教師は、自分の個人クラス チーム内の設定をオフにすることで、ダイジェストをオプトアウトできます ([割り当て]**設定 >/保護者** のメール)。

保護者がメールを受け取るのを確認するには、次の 3 つの項目が true である必要があります。

 - SDS で学生のプロフィールに添付され、親または保護者としてタグ付 _けされた_ メール _アドレス。_ 詳細については、「親と保護者の [同期ファイル形式」を参照してください](/schooldatasync/parent-contact-sync-file-format)。

 - 学生は、課題設定で教師がメールを無効にしていない少なくとも 1 つのクラス [に属しています](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)。

 - メールには、前の週または来週に期限が設定された割り当てに関する情報が含されます。

この機能の既定の設定は - **オフです**。


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode は、すべての学生にコンピューター サイエンスを生き生きとさせるブロックベースのコーディング プラットフォームです。 

MakeCode は、Microsoft の使用条件とプライバシー ポリシーの [対象となる](https://go.microsoft.com/fwlink/?LinkID=206977) Microsoft [製品](https://go.microsoft.com/fwlink/?LinkId=521839) です。

この機能の既定の設定は - **オフです**。

Teams で MakeCode の割り当てを有効にするには **、Teams** 管理センター に移動し、[割り当て] セクションに **移動** し、[MakeCode] トグル オプションを [オン] に **切り替します**。 **[保存]** をクリックします。 これらの設定を有効にするために数時間を許可します。

この機能のしくみの詳細については、このビデオデモを [参照してください](https://makecode.com/blog/teams/teams-assignments)。

[MakeCode の詳細については、 を参照してください](https://aka.ms/makecode)。

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin は](https://www.turnitin.com/) 教育機関向け整合性サービスです。 これは、独自の使用条件とプライバシー ポリシーの対象となるサード パーティの製品またはサービスです。 お客様は、サード パーティの製品およびサービスを使用する責任を負います。

この機能の既定の設定は - **オフ** です。

組織で Turnitin を有効にするには、Turnitin サブスクリプションが必要です。 次に、Turnitin 管理コンソールで確認できる次の情報を入力できます。

  * **TurnitinApiKey:** 管理コンソールの [統合] にある 32 文字の GUID です。
  * **TurnitinApiUrl:** これは、Turnitin 管理コンソールの HTTPS URL です。

この情報の取得に役立つ手順を次に示します。

**TurnitinApiUrl は**、管理コンソールのホスト アドレスです。
例: `https://your-tenant-name.turnitin.com`

管理コンソールでは、統合と、統合に関連付けられている API キーを作成できます。

サイド **メニューから [統合** ] を選択し、[統合の追加] **を選択** し、統合に名前を付きます。

![新しい統合の追加を示すスクリーンショット](./educationImages/Assignments_mopo_turnitin2.png)

**プロンプトに従った後、TurnitinApiKey** が表示されます。 API キーをコピーし、管理センター Microsoft Teams貼り付けます。  キーを表示できるのは今回のみです。

![API キーのコピーを示すスクリーンショット](./educationImages/Assignments_mopo_turnitin3.png)

この設定 **に対して** 管理センターの [保存] ボタンをクリックすると、これらの設定が有効になります。