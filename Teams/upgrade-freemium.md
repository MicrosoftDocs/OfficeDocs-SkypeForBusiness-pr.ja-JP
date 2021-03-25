---
title: 無料版の Microsoft Teams をサブスクリプションにアップグレードする
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
search.appverid: MET150
description: ユーザー向け Microsoft 365 または Office 365 サブスクリプション プランを購入して、無料版の Microsoft Teams から完全版に簡単にアップグレードする方法について説明します。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c4b95081be4c7a0e900099dd4c81a1807a30bfb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122161"
---
# <a name="upgrade-microsoft-teams-free-to-subscription-version"></a>無料版の Microsoft Teams をサブスクリプションバージョンにアップグレードする

組織で無料版の Microsoft Teams を使用している場合は、ユーザー用に Microsoft 365 または Office 365 サブスクリプション プランを購入すると、完全版に簡単にアップグレードできます。 完全版では、無料版では提供されていない、スケジュール、電話会議、強化された管理、セキュリティ機能など、Teams のその他の機能が提供されます。 Microsoft 365 および Office 365 は、使い慣れた Microsoft Office デスクトップ スイートと、Exchange Online、SharePoint Online、Office などの Microsoft の次世代通信およびコラボレーション サービスのクラウドベースバージョンを組み合わせて、ユーザーがインターネットを介して事実上どこからでも生産性を向上するのに役立ちます。 Teams をアップグレードすると、既存の Teams データは失われることはありません。すべてのチーム、チャネル、チャット、ファイル、アクセス許可が提供されます。 

> [!NOTE]
> Microsoft 365 または Office 365 サブスクリプションを既に持っている場合は、無料版ではなく、(会社の ID で) Teams の試用版を利用できます。 Teams の試用版では、Teams の完全バージョンが一限り提供されます。 詳細については [、「Microsoft Teams 商用クラウド試用版のオファーを管理する」を参照してください](./teams-exploratory.md)。

## <a name="how-does-teams-free-compare-to-the-full-version-of-teams"></a>Teams の無料版と Teams の完全版の比較

無料版の Teams は、中小企業向けで設計され、次の機能があります。

- 最大ユーザー数は 500,000 人
- 無制限のチャット メッセージと検索
- ゲスト アクセス
- Word、Excel、PowerPoint、OneNote のオンライン バージョンを含むアプリやサービスとの統合
- ユーザー 1 人あたり 2 GB のストレージと 10 GB の共有ストレージ
- 1:1 およびオンライン音声通話とビデオ通話をグループ化する
- チャネル会議
- 画面共有

Microsoft 365 または Office 365 サブスクリプションに含まれる Teams の完全バージョンには、無料版の Teams で提供される機能に加えて、次の機能が提供されます。

- ユーザー制限なし (エンタープライズ ライセンスを使用)
- Exchange メール ホスティングとカスタム メール ドメイン
- OneDrive、SharePoint、Planner、Yammer、その他の Microsoft 365 および Office 365 サービス
- ユーザー 1 人あたり 1 TB のストレージ
- スケジュールされた会議
- 電話会議
- 多要素認証、シングル サインオン、高度な監査とレポートなど、セキュリティおよびコンプライアンス機能の強化
- 24 x 7 の電話と Web サポート、ユーザーとアプリを管理するための管理ツール、Microsoft 365 または Office 365 サービスの利用状況レポート、サービス レベルアグリーメント、構成可能なユーザー設定とポリシーなどの管理コントロールとサポート機能

無料版の Teams と Teams の機能の詳細な比較については、「Teams プランを比較 [する」を参照してください](https://products.office.com/microsoft-teams/free)。

## <a name="upgrade-requirements"></a>アップグレードの要件

次の要件を満たしている場合は、Teams の完全バージョンにアップグレードできます。

- 既存の無料版 Teams サブスクリプションにサインアップしたユーザーです。
- 独自のドメインを持ち込む場合は、Azure Active Directory にまだ関連付け済みではない (試用版を使用するか、Microsoft 365 または Office 365 サブスクリプションを購入した)。

> [!NOTE]
> データをアップグレードして転送するには、Teams アプリケーションのアップグレード プロセスを通じてサブスクリプションを購入する必要があります。 アップグレード プロセスを実行せずに Teams で Microsoft 365 または Office 365 を購入した場合、別のテナントが既に存在し、データを転送できません。

## <a name="limitations"></a>制限事項

次の制限事項に注意してください。

- アップグレード後、無料版の Teams に切り替えらなんか切り替えはできない。
- 無料版の複数の Teams テナントを 1 つの有料テナントに結合できません。
- すべてのユーザーが同じドメインに登録されている必要があります。 (すべてのユーザーがユーザー名の形式でサインインを受け取 *る* @*domain.com*.)
- すべてのユーザーをアップグレードする必要があります。同じテナント内の無料の Teams と有料のサブスクリプション ユーザーの組み合わせはサポートされません。

## <a name="how-do-i-upgrade-my-organization"></a>組織をアップグレードする方法

フル バージョンの Teams にアップグレードするには、Teams で **[アップグレード]** を選択します。

![[アップグレード] ボタンを示すスクリーンショット](media/teams-freemium-upgrade-image1.png)

Teams へのサインインに使用するメール アドレスを入力し、Microsoft 365 Business Standard プランを購入します。 Microsoft 365 Business Basic または Enterprise エディションの Office 365 を購入する場合は、サポートにお問い [合わせください](https://portal.office.com/support/altusupport.aspx?app=teamsfreeupgrade)。

## <a name="whats-next"></a>次に何をしますか?

アップグレードが完了したら、最初の手順については [「Microsoft Teams](get-started-with-teams-quick-start.md) の使用を開始する」を参照し、組織全体で Teams の導入に段階的にアプローチするために [Microsoft Teams](adopt-microsoft-teams-landing-page.md) を導入する方法を参照してください。

## <a name="more-information"></a>詳細情報

- Teams のバージョンとその機能の詳細については、「Teams プランを比較 [する」を参照してください](https://products.office.com/microsoft-teams/free)。
- フル バージョンの Teams へのアップグレードの詳細については、「無料版の Teams から Teams にアップグレードする」を [参照してください](https://support.office.com/article/Upgrade-from-Teams-free-to-Teams-29475bbd-a34f-4175-9b33-d44430f8ad39)。
- ユーザー ライセンスの追加、ユーザー名の変更、一時パスワードの割り当てなど、ユーザーのアップグレードに関連する追加の管理タスクについては、「 [無料版の Teams](https://support.office.com/article/for-admins-upgrading-from-teams-free-to-a-paid-subscription-75a95e7f-001e-42d0-a787-ae8b992d5a52)から有料サブスクリプションにアップグレードする管理者向け」を参照してください。
- 組織内で無料版の Teams を管理する方法については、「Microsoft Teams の無料版を管理する」 [を参照してください](manage-freemium.md)。