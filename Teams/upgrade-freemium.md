---
title: Microsoft Teams を無料で Office 365 月額プラン バージョンにアップグレードする
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 12/20/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: 無料版の Microsoft Teams をアップグレードする方法について
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ccc20ae70b21e5a6738c8a0956b7c73cff8b7b9
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792703"
---
<a name="upgrade-microsoft-teams-free-to-office-365-subscription-version"></a>Microsoft Teams を無料で Office 365 月額プラン バージョンにアップグレードする
======================================================

組織で Microsoft Teams の無料バージョンを使用している場合は、ユーザーの Office 365 サブスクリプションプランを購入すると、簡単に製品版にアップグレードできます。 フルバージョンでは、スケジュール、電話会議、強化された管理、セキュリティ機能など、無料版では提供されていないその他の Teams 機能が提供されています。 Office 365 は、使い慣れた Microsoft Office デスクトップスイートと、Exchange Online、SharePoint Online、Office などの Microsoft の次世代通信とコラボレーションサービスのクラウドベースのバージョンと組み合わせることで、ユーザーの生産性を向上させることができます。インターネット上でも実質上どこでも利用できます。 チームをアップグレードしても、既存のチームデータは失われません。すべてのチーム、チャネル、チャット、ファイル、権限が追加されました。 

> [!NOTE]
> Office 365 サブスクリプションを既にお持ちの場合は、無料バージョンではなく、Teams の試用版 (会社の id が含まれます) を対象としています。 Teams 試用版では、期間限定で Teams のフルバージョンが提供されます。 詳細については、「 [Microsoft Teams の商用クラウド試用版を管理する](iw-trial-teams.md)」を参照してください。

## <a name="how-does-teams-free-compare-to-the-full-version-of-teams"></a>Teams を無料版の Teams と比較する方法を教えてください。

無料版の Teams は小 ~ 中規模のビジネス向けに設計されており、次のような機能があります。

- 300最大ユーザー数
- 無制限のチャットメッセージと検索
- ゲスト アクセス
- オンラインバージョンの Word、Excel、PowerPoint、OneNote などのアプリとサービスとの統合
- ユーザーあたり 2 GB、共有記憶域 10 GB
- 1:1 とグループのオンライン音声とビデオ通話
- チャネル会議
- 画面共有

Office 365 サブスクリプションに含まれているすべてのチームのバージョンには、無料で提供される機能に加えて、次の機能が用意されています。

- ユーザー制限なし (エンタープライズライセンスあり)
- Exchange メールホスティングとカスタムメールドメイン
- OneDrive、SharePoint、Planner、Yammer、その他の Office 365 サービス
- ユーザーあたり 1 TB のストレージ
- スケジュールされた会議
- 電話会議
- 多要素認証、シングルサインオン、高度な監査とレポートなど、強化されたセキュリティ機能とコンプライアンス機能
- 24 x 7 の電話と web のサポート、ユーザーとアプリを管理するための管理ツール、Office 365 サービスの使用状況レポート、サービスレベル契約、および構成可能なユーザー設定とポリシーを含む、管理コントロールとサポート機能

Teams の無料機能と Teams 機能の詳細については、「[チームプランの比較](https://products.office.com/microsoft-teams/free)」を参照してください。

## <a name="upgrade-requirements"></a>アップグレードの要件

次の要件を満たしている場合は、フルバージョンの Teams にアップグレードすることができます。

- 既存の Teams 無料サブスクリプションにサインアップしたユーザーです。
- 独自のドメインを使用している場合は、既に Azure Active Directory に関連付けられていない (試用版または購入済みの O365 サブスクリプション経由)。

> [!NOTE]
> データをアップグレードして転送するには、Teams アプリケーションのアップグレードプロセスを通じてサブスクリプションを購入する必要があります。 アップグレードプロセスを行わずに Teams で Office 365 を購入した場合は、既に別のテナントがあるため、データを転送することはできません。

## <a name="limitations"></a>伴う

次の制限事項を念頭に置いてください。

- アップグレードした後は、無料で Teams に戻すことはできません。
- 複数の Teams 無料テナントを1つの有料テナントに統合することはできません。
- すべてのユーザーが同じドメインに存在する必要があります。 (すべてのユーザーは、 *username*@*domain.com*の形式でサインインします)。
- すべてのユーザーをアップグレードする必要があります。同じテナントに Teams の無料サブスクリプションユーザーと有料サブスクリプションの両方を混在させることはできません。

## <a name="how-do-i-upgrade-my-organization"></a>組織をアップグレードするにはどうすればよいですか?

フルバージョンの Teams にアップグレードするには、[Teams で**アップグレード**] を選択します。

![[アップグレード] ボタンを示すスクリーンショット](media/teams-freemium-upgrade-image1.png)

Teams へのサインインに使用するメールアドレスを入力して、Office 365 Business Premium プランを購入します。 Office 365 Business Essentials または Enterprise edition の Office 365 を購入する場合は、[サポートにお問い合わせ](https://portal.office.com/support/altusupport.aspx?app=teamsfreeupgrade)ください。

## <a name="whats-next"></a>次の作業

アップグレードが完了したら、最初の手順については、「 [Microsoft teams の使用を開始](get-started-with-teams-quick-start.md)する」および「 [microsoft teams](adopt-microsoft-teams-landing-page.md)を組織全体でのチームの導入への段階的アプローチに採用する」を参照してください。

## <a name="more-information"></a>詳細情報

- チームのバージョンとその機能の詳細については、「[チームの計画を比較](https://products.office.com/microsoft-teams/free)する」を参照してください。
- Teams のフルバージョンへのアップグレードの詳細については、「無料の teams[から teams にアップグレードする](https://support.office.com/article/Upgrade-from-Teams-free-to-Teams-29475bbd-a34f-4175-9b33-d44430f8ad39)」を参照してください。
- ユーザーのアップグレードに関連するその他の管理タスク (ユーザーライセンスの追加、ユーザー名の変更、一時パスワードの割り当てなど) については、「[無料のサブスクリプションから有料のサブスクリプションにアップグレードするための管理者向け](https://support.office.com/article/for-admins-upgrading-from-teams-free-to-a-paid-subscription-75a95e7f-001e-42d0-a787-ae8b992d5a52)」を参照してください。
- 組織内のチームを無料で管理する方法については、「 [Microsoft Teams の無料バージョンを管理](manage-freemium.md)する」を参照してください。

