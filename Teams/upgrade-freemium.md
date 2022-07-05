---
title: Microsoft Teams 無料版 (クラシック)をサブスクリプションにアップグレードする
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
search.appverid: MET150
description: Microsoft Teams の無料版からフル バージョンに簡単にアップグレードするには、ユーザー向けに Microsoft 365 またはOffice 365サブスクリプション プランを購入する方法について説明します。
ms.localizationpriority: medium
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
ms.openlocfilehash: 123cb6343886f269a847d431b87f154855086d9b
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615743"
---
# <a name="upgrade-microsoft-teams-free-classic-to-subscription-version"></a>Microsoft Teams 無料版 (クラシック)をサブスクリプション バージョンにアップグレードする

組織で Microsoft Teams の無料版を使用している場合は、ユーザーの Microsoft 365 またはOffice 365サブスクリプション プランを購入することで、完全版に簡単にアップグレードできます。 フル バージョンには、スケジュール設定、電話会議、強化された管理、セキュリティ機能など、無料版では提供されない追加の Teams 機能が用意されています。 Microsoft 365 とOffice 365は、使い慣れた Microsoft Office デスクトップ スイートと、Exchange Online、SharePoint Online、Office などの次世代通信およびコラボレーション サービスのクラウドベースバージョンを組み合わせて、ユーザーがインターネットを介して事実上どこからでも生産性を高めるのに役立ちます。 Teams をアップグレードしても、既存の Teams データは失われません。すべてのチーム、チャネル、チャット、ファイル、アクセス許可が付属しています。

> [!NOTE]
> Microsoft 365 または Office 365 サブスクリプションを既に所有している場合は、無料版ではなく、(会社の ID を使用して) Teams の試用版の対象となります。 Teams 試用版では、限られた期間、Teams の完全なバージョンが提供されます。 詳細については、「 [Microsoft Teams 商用クラウド 試用版プランの管理](./teams-exploratory.md)」を参照してください。

## <a name="how-does-teams-free-classic-compare-to-the-full-version-of-teams"></a>Teams Free (クラシック) は Teams のフル バージョンとどのように比較されますか?

Teams Free (クラシック) は、中小企業向けに設計されており、次の機能があります。

- 最大ユーザー数 500,000 人
- 無制限のチャット メッセージと検索
- ゲスト アクセス
- Word、Excel、PowerPoint、OneNote のオンライン バージョンを含むアプリやサービスとの統合
- ユーザーあたり 2 GB のストレージと 10 GB の共有ストレージ
- 1:1 とグループのオンラインオーディオとビデオ通話
- チャネル会議
- 画面共有

Microsoft 365 または Office 365 サブスクリプションに含まれる Teams のフル バージョンには、Teams が無料で提供する機能に加えて、次の機能が用意されています。

- ユーザー制限なし (エンタープライズ ライセンスあり)
- Exchange メール ホスティングとカスタム電子メール ドメイン
- OneDrive、SharePoint、Planner、Yammer、その他の Microsoft 365 およびOffice 365 サービス
- ユーザーあたり 1 TB のストレージ
- 予約された会議
- 電話会議
- 多要素認証、シングル サインオン、監査 (Premium) の作成とレポート作成など、セキュリティとコンプライアンスの強化された機能
- 24 x 7 の電話および Web サポート、ユーザーとアプリを管理するための管理ツール、Microsoft 365 またはOffice 365 サービスの使用状況レポート、サービス レベル アグリーメント、構成可能なユーザー設定とポリシーなど、管理コントロールとサポート機能

Teams Free (クラシック) 機能と Teams 機能の詳細な比較については、「 [Teams プランの比較](https://products.office.com/microsoft-teams/free)」を参照してください。

## <a name="upgrade-requirements"></a>アップグレードの要件

次の要件を満たしている場合は、Teams のフル バージョンにアップグレードできます。

- あなたは、既存の Teams 無料サブスクリプションにサインアップしたユーザーです。
- 独自のドメインを持ち込む場合は、Azure Active Directory にまだ関連付けられていない (試用版または購入された Microsoft 365 または Office 365 サブスクリプションを使用)。

> [!NOTE]
> データをアップグレードして転送するには、Teams アプリケーションのアップグレード プロセスを通じてサブスクリプションを購入する必要があります。 アップグレード プロセスを経ずに Teams で Microsoft 365 または Office 365を購入した場合は、既に別のテナントがあるため、データを転送できません。

## <a name="limitations"></a>制限事項

次の制限事項に留意してください。

- アップグレード後に Teams Free (クラシック) に切り替えることはできません。
- 複数の Teams Free (クラシック) テナントを 1 つの有料テナントにマージすることはできません。
- すべてのユーザーは同じドメインに属している必要があります。 (すべてのユーザーは、*ユーザー名*@の形式でサインインを取得します。*domain.com*.)
- すべてのユーザーをアップグレードする必要があります。同じテナント内の Teams Free (クラシック) ユーザーと有料サブスクリプション ユーザーの組み合わせがサポートされていません。

## <a name="how-do-i-upgrade-my-organization"></a>組織をアップグレードするにはどうすればよいですか?

Teams のフル バージョンにアップグレードするには、Teams で **[アップグレード** ] を選択します。

![[アップグレード] ボタンを示すスクリーンショット。](media/teams-freemium-upgrade-image1.png)

Teams へのサインインに使用する電子メール アドレスを入力し、Microsoft 365 Business Standard プランを購入します。 Microsoft 365 Business Basicまたは Office 365 の Enterprise エディションを購入する場合は、[サポートにお問い合わせください](https://portal.office.com/support/altusupport.aspx?app=teamsfreeupgrade)。

## <a name="whats-next"></a>次は何ですか?

アップグレードが完了したら、最初の手順については [「Microsoft Teams の使用を開始](get-started-with-teams-quick-start.md) する」を参照し、組織全体の Teams の導入に対する段階的なアプローチに [Microsoft Teams を採用](adopt-microsoft-teams-landing-page.md) します。

## <a name="more-information"></a>詳細情報

- Teams のバージョンとその機能の詳細については、「 [Teams プランの比較](https://products.office.com/microsoft-teams/free)」を参照してください。
- Teams のフル バージョンへのアップグレードの詳細については、「 [Teams Free (クラシック) から Teams へのアップグレード](https://support.office.com/article/Upgrade-from-Teams-free-to-Teams-29475bbd-a34f-4175-9b33-d44430f8ad39)」を参照してください。
- ユーザー ライセンスの追加、ユーザー名の変更、一時的なパスワードの割り当てなど、ユーザーのアップグレードに関連するその他の管理者タスクについては、「 [Teams Free (クラシック) から有料サブスクリプションにアップグレードする管理者](https://support.office.com/article/for-admins-upgrading-from-teams-free-to-a-paid-subscription-75a95e7f-001e-42d0-a787-ae8b992d5a52)向け」を参照してください。
- 組織内で Teams を無料で管理する方法については、「 [Microsoft Teams の無料版を管理する」を](manage-freemium.md)参照してください。