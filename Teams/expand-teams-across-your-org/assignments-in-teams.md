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
description: Teams for Education で Microsoft Teams 管理センターで課題を管理する方法について説明します。
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

Teams for Education の課題と成績の機能を使用すると、教師は学生にタスク、作業、またはテストを割り当てできます。 教師は、課題のタイムライン、手順の管理、割り当てに必要なリソースの追加、ルーブリックを使用した成績の評価など、その他の操作を行えます。 また、[成績] タブでクラスと個々の学生の進捗状況を追跡することもできます。

[Teams for Education の課題と成績の詳細については、次を参照してください](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)。

> [!Note]
> さまざまなプラットフォームでの Teams の割り当ての詳細については、プラットフォーム別 [の Teams の機能を参照してください](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでの課題の統合

Microsoft Teams 管理センターの管理者設定を使用して、組織内の教師とその学生の機能を有効またはオフにできます。 課題に関連する設定を次に示します。

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>週刊保護者用メール ダイジェスト


保護者のメールは、週末ごとに保護者に送信されます。 メールには、前の週と来週の課題に関する情報が含まれている。 School Data Sync を使用して親と [保護者の同期をセットアップできます](/schooldatasync/parent-contact-sync)。

1. SDS で保護者の同期を使用して親の連絡先情報をインポートします。 保護者と保護者の同期を有効にする方法については、「親と保護者の同期を有効にする [」を参照してください](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)。

2. 設定は既定でオフになっているので、Microsoft Teams 管理センターで [Guardian 設定] をオンにします。 これにより、教師は週刊ダイジェストを送信できます。

   > [!NOTE]
   > 教師は、自分の個人クラス チーム内の設定を選択解除して、ダイジェストからオプトアウトすることができます ([課題の設定] >**親/保護者のメール**)。

保護者がメールを受け取るのを確認するには、次の 3 つの項目を満たしている必要があります。

 - SDS で学生のプロファイルに添付され、親または保護者としてタグ付けされたメール _アドレス_。 詳細については、「親と [保護者の同期ファイル形式」を参照してください](/schooldatasync/parent-contact-sync-file-format)。

 - 学生は、課題設定で教師がメールを無効にしていない少なくとも 1 つのクラス [に属しています](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)。

 - メールには、前の週または来週に期限が設定された課題に関する情報が含されます。

この機能の既定の設定は - オフ **です**。


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode は、すべての学生にコンピューター 科学を生き生きとさせるブロックベースのコーディング プラットフォームです。 

MakeCode は、Microsoft の使用条件とプライバシー ポリシーの適用 [対象となる](https://go.microsoft.com/fwlink/?LinkID=206977) Microsoft [製品](https://go.microsoft.com/fwlink/?LinkId=521839) です。

この機能の既定の設定は - オフ **です**。

Teams で MakeCode の割り当てを有効にするには **、Teams** 管理センターに移動し、[割り当て] セクションに移動し、[MakeCode] トグル オプションを [オン]**に切** り替える。 **[保存]** をクリックします。 これらの設定が有効な場合は、数時間かかります。

この機能の詳細については、このビデオのデモを [参照してください](https://makecode.com/blog/teams/teams-assignments)。

[MakeCode の詳細については、次を参照してください](https://aka.ms/makecode)。

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin は](https://www.turnitin.com/) 教育機関向け整合性サービスです。 これは、独自の条項とプライバシー ポリシーの適用対象となるサード パーティ製品またはサービスです。 お客様は、サード パーティの製品およびサービスの使用について責任を負います。

この機能の既定の設定は - **オフ**..

組織で Turnitin を有効にするには、Turnitin サブスクリプションが必要です。 その後、Turnitin 管理コンソールで次の情報を入力できます。

  * **TurnitinApiKey:** これは、管理コンソールの [統合] にある 32 文字の GUID です。
  * **TurnitinApiUrl**: Turnitin 管理コンソールの HTTPS URL です。

この情報を取得するのに役立ついくつかの手順を次に示します。

**TurnitinApiUrl** は管理コンソールのホスト アドレスです。
例: `https://your-tenant-name.turnitin.com`

管理コンソールでは、統合と統合に関連付けられた API キーを作成できます。

サイド **メニューから [** 統合] を選択し、[統合の追加] を **選択し、** 統合に名前を付きます。

![新しい統合の追加を示すスクリーンショット](./educationImages/Assignments_mopo_turnitin2.png)

画面 **の指示に従った後、TurnitinApiKey** が表示されます。 API キーをコピーし、Microsoft Teams 管理センターに貼り付けます。  キーを表示できるのは今回のみです。

![API キーのコピーを示すスクリーンショット](./educationImages/Assignments_mopo_turnitin3.png)

管理センター **でこの設定** の [保存] ボタンをクリックすると、これらの設定が有効なのに数時間かかります。