---
title: Teams での割り当て
author: lanachin
ms.author: v-lanac
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
description: 教育担当の Teams で Microsoft Teams 管理センターの課題を管理する方法について説明します。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3a0bf0dd0141679dc89ed1d5ecc0cfc542854c8
ms.sourcegitcommit: 3eb5820b279fc904f34ac4259deeb419e02d832a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561053"
---
# <a name="assignments-in-teams-for-education"></a>教育機関向けの Teams の課題 

割り当ては、学生またはチームメンバーに対して、調査の一環として、クラス内で割り当てられているタスクまたは作業単位数です。 Teams クラス内で課題を作成することができます。

[割り当ての詳細について](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)は、こちらを参照してください。

> [!Note]
> さまざまなプラットフォームでの Teams の割り当てについて詳しくは、「 [プラットフォームごとの teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」をご覧ください。

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでの課題

Microsoft Teams 管理センターの管理設定を使用すると、組織内の学生と教師が、次の機能を有効または無効にすることができます。 課題に関連する設定を次に示します。

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>1週間のガーディアンメールダイジェスト

このメールには、前週と来週の課題に関する情報が含まれており、週末に送信されます。 メールコンテンツに関する情報については、こちらを参照してください。 メールは、 [School Data Sync (SDS)](https://docs.microsoft.com/schooldatasync/)を使用して管理者がセットアップおよび更新する必要があります。 この機能は、学校の学生情報システム (SIS) を使用して、学生の選手名簿で Teams のクラスを自動的に設定します。 この機能を有効にするには、次の手順を実行します。

1. SDS で親とガーディアンの同期を使って、親の連絡先情報をインポートします。 親とガーディアンの同期を有効にする方法については、「 [親とガーディアンの同期を有効](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)にする」を参照してください。

2. 設定は既定で無効になっているため、Microsoft Teams 管理センターで [ガーディアン] 設定をオンにします。 これにより、教師が毎週のダイジェストを送信できるようになります。

   > [!NOTE]
   > 教師は、独自の個人用クラスチーム内の設定 (**親/ガーディアンメール > の割り当て設定**) の選択を解除することによって、ダイジェストを除外することができます。

親からメールが送信されることを確認するには、次の3つの項目が true である必要があります。

 - SDS の学生プロファイルに添付され、 _親_ または _ガーディアン_ としてタグ付けされたメールアドレス。 詳細については、「 [親とガーディアンの同期ファイル形式](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format)」を参照してください。

 - 学生は、[ [割り当ての設定](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)] の教師によって無効にされていない1つ以上のクラスに属しています。

 - このメールには、先週または来週に期限がある課題に関する情報が含まれています。

この設定は、既定ではオフになっています。


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode はブロックベースのコーディングプラットフォームであり、すべての学生に対してコンピューターの科学を実現します。 

MakeCode は、Microsoft [利用規約](https://go.microsoft.com/fwlink/?LinkID=206977) および [プライバシー](https://go.microsoft.com/fwlink/?LinkId=521839) ポリシーの適用対象となる microsoft 製品です。

この設定は、既定ではオフになっています。 Teams で MakeCode の割り当てを有効にするには、 **Teams 管理センター** で、[ **課題** ] セクションに移動し、MakeCode トグルオプションを **[オン**] にします。 [ **保存** ] をクリックして、これらの設定が有効になるまで数時間待ちます。

この機能のしくみについて詳しくは、この [ビデオデモ](https://makecode.com/blog/teams/teams-assignments)をご覧ください。

[MakeCode の詳細について](https://aka.ms/makecode)は、こちらを参照してください。

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin は、plagiarism の検出サービスです。 これは、サードパーティの製品またはサービスであり、独自の用語とプライバシーポリシーの適用対象となります。 お客様は、サードパーティの製品とサービスの使用に関して責任を負います。

この設定は、既定ではオフになっています。

組織の Turnitin を正常に有効にするには、Turnitin サブスクリプションが既に存在している必要があります。 次の追加情報を入力する必要があります。これは、Turnitin の管理コンソールにあります。

  * **TurnitinApiKey**: この32文字の GUID は、[統合] の下の管理コンソールにあります。
  * **TurnitinApiUrl**: これは、Turnitin 管理コンソールの HTTPS URL です。

この情報を取得するための手順をいくつか紹介します。

**TurnitinApiUrl** は、管理コンソールのホストアドレスです。
次 `https://your-tenant-name.turnitin.com`

管理コンソールでは、統合と関連付けられた API キーを作成できます。

サイド **メニューから [統合] を選択** し、[ **統合の追加** ] を選択して、統合の名前を指定します。

![新しい統合の追加を示すスクリーンショット](./educationImages/Assignments_mopo_turnitin2.png)

プロンプトが表示された後、 **TurnitinApiKey** が提供されます。 API キーをコピーして、Microsoft Teams 管理センターに貼り付けます。  これは、キーを表示できる唯一の時間です。

![API キーのコピーを示すスクリーンショット](./educationImages/Assignments_mopo_turnitin3.png)

この設定のために管理センターで [ **保存** ] ボタンをクリックしたときに、これらの設定が有効になるまで、数時間許可してください。

Teams で Turnitin 統合の使用を開始する準備ができましたか? [以前のアクセスプログラム](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)にサインアップします。
