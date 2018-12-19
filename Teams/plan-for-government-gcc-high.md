---
title: マイクロソフト チームが Microsoft 365 政府の GCC の高い展開の計画します。
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 12/18/2018
ms.topic: article
ms.service: msteams
ms.reviewer: daro
description: 米国政府の規制の対象となるデータを処理するエンティティでドライブ Office 365 の展開を IT プロフェッショナルのためのガイダンスです。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08e2c2d93aa38d41c8965b622aaa5a5b51652061
ms.sourcegitcommit: bb4e7dec155dee358bec9d6e586730dae0b8f559
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2018
ms.locfileid: "27374783"
---
# <a name="plan-for-microsoft-365-government---gcc-high-deployments"></a>Microsoft 365 政府の GCC の高い展開の計画

米国連邦政府機関での Office 365 の導入を促進する IT プロフェッショナルまたは Microsoft 365 政府 – GCC 高の使用が適切な政府の規制の対象となるデータと要件を処理する他のエンティティには、このガイドこれらの要件に対応します。

> [!NOTE]
> 組織が既に Microsoft 365 政府 – GCC 高の適格性の要件が満たされるとに適用され、プログラムに受け入れられた、1 ~ 4 の手順をスキップして、展開を開始するのには 5 の手順に進みます。

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-high-and-meets-eligibility-requirements"></a>手順 1 です。 組織が Microsoft 365 政府 - を GCC 高の必要があるあり、適格性の要件を満たしているかどうかを決定します。 

Microsoft 365 政府の GCC の高い環境では、クラウド サービスの政府の要件米国への準拠を提供します。 Office 365 の機能を楽しむだけでなくは、組織は、対象の Microsoft 365 政府 – GCC 高次の機能を活用できます。

- 組織の顧客のコンテンツが Microsoft の商用の Office 365 サービスでお客様のコンテンツ論理的に分離します。
- 組織の顧客のコンテンツは、米国内に格納されます。
- 組織の顧客のコンテンツへのアクセスは、スクリーンの Microsoft の担当者に限定されます。
- 証明書および米国の公的機関のお客様に必要な認定と GCC の高い Microsoft 365 の政府が準拠しています。

Microsoft 365 政府 – GCC 高の米国政府の[Office 365 の政府の計画](https://products.office.com/government/compare-office-365-government-plans)などの[特典を受ける](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)お客様は、製品の詳細についてを見つけることができます。

[Office 365 の米国政府のサービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)は、プラットフォームの利点は、米国内でのコンプライアンス要件を満たすことを中心に説明します。


> [!Tip]
> サービスの説明内の情報のテーブルを Excel ブックに転送し、2 つの列を追加することができます:**はい/いいえ、組織内での関連性**と**Y か N は、自分の組織のニーズに対応**します。 このサービスが組織のニーズを満たしていることを確認するのには、同僚と、この一覧を確認できます。


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft 365 政府の GCC の高が組織にとって適切かどうかを決定します。</li><li>組織が適格性の要件を満たしていることを確認します。</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>Microsoft 365 政府の GCC 高によって提供される機能を理解します。</li></ul>|

> [!Note]
> Microsoft 365 政府の GCC 高には、アメリカ合衆国ではできるだけです。 -米国以外の政府機関のお客様は、いくつかの[Office 365 の政府の計画](https://products.office.com/en/government/compare-office-365-government-plans)から選択できます。

## <a name="step-2-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>手順 2 です。 機能は、現在利用できないか、既定で無効になっているを理解します。 

政府クラウドのお客様の要件に対応するためには、Microsoft 365 政府の GCC 高とエンタープライズのプランをいくつかの違いがあります。 どの機能が使用できるかを確認するのには次の表を参照してください。

|                             | 機能                     | GCC 高       |
|-----------------------------|-----------------------------|----------------|
| ベース | ログイン | 利用可能 |
| | プレゼンス | 利用可能 |
| | 統合されたプレゼンス (Skype のビジネスと統合チーム) | 政府のバックログに |
| アクティビティ | フィード | 利用可能 |
|  | マイ アクティビティ | 利用可能 |
| チャット | 会話 | 利用可能 |
| | ファイル | 利用可能 |
| | 組織図 | 利用可能 |
| | アクティビティ | 利用可能 |
| | 相互運用機能 (1:1 チームの Skype ビジネス チャット用) | 政府のバックログに |
| Teams | チャンネル メッセージ | 利用可能 |
| | チャンネル ファイル | 利用可能 |
| | OneNote] タブ | 政府のバックログに |
| | チャネルを電子メールで送信します。 | 該当なし |
| | メンバーを追加します。 | 利用可能 |
| | ゲスト アクセス | 政府のバックログに |
| 会議 | 会議のスケジュール | 利用可能 |
| | ミーティングへの参加します。 | 利用可能 |
| | VoIP 会議 | 利用可能 |
| | デスクトップの共有 | 利用可能 |
| | やり取りのコントロールの共有 | 利用可能 |
| | 会議室からの接続します。 | 利用可能 |
| | 匿名の結合 | 利用可能 |
| | クラウドの記録 | 政府のバックログに |
| | 会議ノート | 利用可能 |
| | 会議をブロードキャストします。 | 政府のバックログに |
| | 連合の会議 | 利用可能 |
| | サーフェス ・ ハブのサポート | 政府のバックログに |
| 通話 | 連絡先 | 利用可能 |
| | 履歴 | 利用可能 |
| | ボイスメール | 利用可能 |
| | VoIP 通話 | 利用可能 |
| | Skype のビジネス ・ チームを呼び出す | 利用可能 |
| | 通話プラン | 利用できません。 |
| | (PSTN を使用して参加するミーティングの参加者を許可する) での音声会議 | 政府のバックログに |
| | マイクロソフトの電話システムの直接のルーティング | 政府のバックログに |
| | PSTN の呼び出し元のロビー | 政府のバックログに |
| | 呼び出しキュー | 政府のバックログに |
| | 上司と代理人のサポート | 政府のバックログに |
| | 提案型で安全な転送 | 政府のバックログに |
| | 画期的なを不可します。 | 政府のバックログに |
| | 「鳴り分け」 | 政府のバックログに |
| | チーム、ビジネス、Skype で通話をグループに 1:1 と PSTN 参加者 | 政府のバックログに |
| | グループへの転送します。 | 政府のバックログに |
| | PSTN 通話を転送します。 | 政府のバックログに |
| | 緊急通話のプランを呼び出す | 政府のバックログに |
| | 認定済みの既存の SIP 電話のサポート | 政府のバックログに |
| | USB の HID | 利用可能 |
| | 通話と会議の両方の電子的証拠開示 | 利用可能 |
| | 組織の自動応答 | 政府のバックログに |
| | Skype 個人向け - チーム呼び出しのサポート | 該当なし |
| ファイル | 最近 | 利用可能 |
| | Microsoft Teams | 利用可能 |
| ストア | アプリケーション ストア | 該当なし |
| 検索 | メッセージ | 利用可能 |
| | ユーザー | 利用可能 |
| | ファイル | 利用可能 |
| | スラッシュ コマンド | 利用可能 |
| コンプライアンス | コンプライアンス ・ コンテンツの検索 | 利用可能 |
| | 保存期間 | 利用可能 |
| | 監査ログの検索 | 利用可能 |
| | 法的保持義務 | 利用可能 |
| | 電子情報開示 | 利用可能 |

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft 365 政府の GCC の高機能のセットが、組織のニーズを満たしているかどうかを決定します。</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>既定のセキュリティ設定を理解します。</li></ul>|

## <a name="step-3-understand-microsoft-365-government---gcc-high-default-security-settings"></a>ステップ 3 です。 Microsoft 365 政府の高い GCC のデフォルトのセキュリティ設定を理解します。

[管理とセキュリティの設定](enable-features-office-365.md)を見直し、それらを変更し、既定のセキュリティ設定を変更する前に、コンプライアンスへの影響を検討する前に時間がかかることをお勧めします。

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft 365 政府の GCC の高セキュリティの設定、既定値のいずれかを変更するかどうかの変更の影響を理解して最初に解決する可能性がありますを行うかを決定します。</li></ul> |

## <a name="step-4-apply-for-microsoft-365-government---gcc-high"></a>手順 4 します。 Microsoft 365 政府の GCC の適用高

決定することはこのサービスは、お客様の組織、[このサービスに適用する](https://products.office.com/government/eligibility-validation)プロセスを開始することです。

## <a name="step-5-plan-for-governance"></a>手順 5 です。 ガバナンスの計画

コーポレート ・ ガバナンスとどのように満たすことがお客様の要件を決定します。 詳細については、[チームの管理のための計画](plan-teams-governance.md)に移動します。

## <a name="step-6-deploy-teams-for-collaboration"></a>手順 6。 チームの共同作業を展開します。

Microsoft 365 政府 – GCC 高では、onboarded をした後、 [FastTrack](https://fasttrack.microsoft.com/fasttrack-faq)とオンボードを選択したパートナーのサービスを使用する標準的な展開アプローチをフォローできます。

準備ができたら、[チーム、およびチャネルを通じて、組織内でのコラボレーションを有効に](teams-overview.md)するチームを展開します。 採用し、変更管理のチームまたはチームのエキスパートと協力することを確認します。
