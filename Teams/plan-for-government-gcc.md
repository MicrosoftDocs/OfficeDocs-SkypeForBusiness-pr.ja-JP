---
title: Microsoft 365 米国政府向けクラウド (GCC) の展開の計画 - Microsoft Teams
author: lolajacobsen
ms.author: lehewe
manager: serdars
ms.date: 01/03/2019
ms.topic: article
ms.service: msteams
ms.reviewer: daro
description: 米国政府の規制の対象となるデータを処理するエンティティでドライブ Office 365 の展開を IT プロフェッショナルのためのガイダンス
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24ceb6ff76bb84f8de9d9248fc4c10a73ee454f4
ms.sourcegitcommit: f5f1437ec72f67f6804ca8d785f76059d0979e39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29890765"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Microsoft 365 政府の GCC の展開の計画

このガイダンスは米国連邦政府、状態、航空写真や民族のお、ローカル政府機関や政府の規制や要件の対象となるデータを処理する他のエンティティで、Office 365 の導入を促進する IT プロフェッショナルには、Microsoft の使用365 政府の GCC は、これらの要件を満たすために適しています。

> [!NOTE]
> 組織が既に Microsoft 365 政府の GCC の適格性の要件が満たされるの適用やプログラムに受け入れられた場合は、1 と 2 の手順をスキップし、ステップ 3 に進みます。 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>手順 1 です。 組織が Microsoft 365 政府の GCC を必要があるし、適格性の要件を満たしているかどうかを決定します。 

Microsoft 365 政府の GCC 環境を提供米国への準拠 FedRAMP 中、刑事裁判および連邦の税情報システム (CJI と FTI のデータ型) の要件など、クラウド サービスの政府の要件。

Office 365 の機能を楽しむだけでなくは、組織はマイクロソフト 365 政府の GCC に固有の以下の機能を活用できます。

-   組織の顧客のコンテンツが Microsoft の商用の Office 365 サービスでお客様のコンテンツ論理的に分離します。
-   組織の顧客のコンテンツは、米国内に格納されます。
-   組織の顧客のコンテンツへのアクセスは、スクリーンの Microsoft の担当者に限定されます。
-   Microsoft 365 政府の GCC は、証明書および米国の公的機関のお客様に必要な認定に準拠します。

Microsoft 365 政府 - 米国政府の[Office 365 の政府の計画](https://products.office.com/government/compare-office-365-government-plans)などの[特典を受ける](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)お客様は、提供する GCC の詳細についてを見つけることができます。

[Office 365 の米国政府のサービスの説明](https://technet.microsoft.com/library/mt774581.aspx)では、プラットフォームの利点は、米国内でのコンプライアンス要件を満たすことの中心は、について説明します。

> [!Tip]
> サービスの説明内の情報のテーブルを Excel ブックに転送し、2 つの列を追加することができます:**はい/いいえ、組織内での関連性**と**Y か N は、自分の組織のニーズに対応**します。 このサービスが組織のニーズを満たしていることを確認するのには、同僚と、この一覧を確認できます。

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft 365 政府の GCC は、組織の適切なかどうかを決定します。</li><li>組織が適格性の要件を満たしていることを確認します。</li></ul> |

> [!Note]
> Microsoft 365 政府の GCC をアメリカ合衆国ではできるだけです。 -米国以外の政府機関のお客様は、いくつかの[Office 365 の政府の計画](https://products.office.com/en/government/compare-office-365-government-plans)から選択できます。


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>手順 2 です。 Microsoft 365 政府の GCC を適用します。

持つことに、このサービスがお客様の組織は、[このサービスは、ここに適用する](https://products.office.com/government/eligibility-validation)プロセスを開始します。

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>ステップ 3 です。 Microsoft 365 政府の GCC のデフォルトのセキュリティ設定を理解します。

[管理とセキュリティの設定](enable-features-office-365.md)を見直し、それらを変更し、既定のセキュリティ設定を変更する前に、コンプライアンスへの影響を検討する前に時間がかかることをお勧めします。

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft 365 政府の GCC のセキュリティ設定を既定値のいずれかを変更するかどうか最初の変更の影響を理解するのには解決を加えたことを決定します。</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>手順 4 します。 機能は、現在利用できないか、既定で無効になっているを理解します。 

Microsoft 365 政府の GCC をいくつかの相違がある、政府のクラウドのお客様の要件に合わせて、およびエンタープライズのプランです。 どの機能が使用できるかを確認するのには次の表を参照してください。

|                             | 機能                     | GCC            |
|-----------------------------|-----------------------------|----------------|
| ベース | ログイン | 利用可能 |
| | プレゼンス | 利用可能 |
| | 統合されたプレゼンス (Skype のビジネスと統合チーム) | 利用可能 |
| アクティビティ | フィード | 利用可能 |
|  | マイ アクティビティ | 利用可能 |
| チャット | 会話 | 利用可能 |
| | ファイル | 利用可能 |
| | 組織図 | 利用可能 |
| | アクティビティ | 利用可能 |
| | 相互運用機能 (1:1 チームの Skype ビジネス チャット用) | 利用可能 |
| Teams | チャンネル メッセージ | 利用可能 |
| | チャンネル ファイル | 利用可能 |
| | OneNote] タブ | 政府のバックログに |
| | チャネルを電子メールで送信します。 | 該当なし |
| | メンバーを追加します。 | 利用可能 |
| | ゲスト アクセス | 利用可能 |
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
| | サーフェス ・ ハブのサポート (プレビュー) | 利用可能 |
| 通話 | 連絡先 | 利用可能 |
| | 履歴 | 利用可能 |
| | ボイスメール | 利用可能 |
| | VoIP 通話 | 利用可能 |
| | Skype のビジネス ・ チームを呼び出す | 利用可能 |
| | 通話プラン | 利用可能 |
| | (PSTN を使用して参加するミーティングの参加者を許可する) での音声会議 | 利用可能 |
| | マイクロソフトの電話システムの直接のルーティング | 利用可能 |
| | PSTN の呼び出し元のロビー | 利用可能 |
| | 呼び出しキュー | 利用可能 |
| | 上司と代理人のサポート | 利用可能 |
| | 提案型で安全な転送 | 利用可能 |
| | 画期的なを不可します。 | 利用可能 |
| | 「鳴り分け」 | 利用可能 |
| | チーム、ビジネス、Skype で通話をグループに 1:1 と PSTN 参加者 | 利用可能 |
| | グループへの転送します。 | 利用可能 |
| | PSTN 通話を転送します。 | 利用可能 |
| | 緊急通話のプランを呼び出す | 利用可能 |
| | 認定済みの既存の SIP 電話のサポート | 利用可能 |
| | USB の HID | 利用可能 |
| | 通話と会議の両方の電子的証拠開示 | 利用可能 |
| | 組織の自動応答 | 利用可能 |
| | Skype 個人向け - チーム呼び出しのサポート | 利用可能 |
| ファイル | 最近 | 利用可能 |
| | Microsoft Teams | 利用可能 |
| ストア | アプリケーション ストア | 政府のバックログに |
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
| ![](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>チームの機能セットが、組織のニーズを満たしているかどうかを決定します。</li></ul> |

## <a name="step-5-plan-for-governance"></a>手順 5 です。 ガバナンスの計画

コーポレート ・ ガバナンスとどのように満たすことがお客様の要件を決定します。 詳細については、[チームの管理のための計画](plan-teams-governance.md)に移動します。

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>決定し、[チームの管理のための計画](plan-teams-governance.md)のガイドラインに従って、・ ガバナンスの要件を文書化します。</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>手順 6。 チームの共同作業を展開します。

Microsoft 365 政府の GCC では、onboarded をした後[FastTrack](https://www.microsoft.com/fasttrack)と、選択したパートナー サービスにオンボードを使用する標準的な展開方法に従います。

準備ができたら、[チーム、およびチャネルを通じて、組織内でのコラボレーションを有効に](teams-overview.md)するチームを展開します。 採用し、変更管理のチームまたはチームのエキスパートと協力することを確認します。

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>手順 7 です。 会議および音声のチームを配置します。

広く利害関係者グループにチームを使用して、会議や[クラウドのボイス機能](cloud-voice-deployment.md)を展開するための計画を開始する絶好の機会です。

