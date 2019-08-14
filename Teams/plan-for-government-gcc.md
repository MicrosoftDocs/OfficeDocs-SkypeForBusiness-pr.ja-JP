---
title: Microsoft 365 米国政府向けクラウド (GCC) の展開の計画 - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/03/2019
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 米国政府規制の対象となるデータを処理するエンティティで Office 365 の展開を推進する IT 担当者向けガイダンス
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 506d33ab48ad35397a500ef8f274ef6a332f8cd1
ms.sourcegitcommit: ab259764dc50bdd52efed3abb1d065ee19486946
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "36393440"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Microsoft 365 Government-GCC 展開を計画する

このガイダンスは、米国連邦、州、地方、tribal、または territorial 政府機関の法人向けの Office 365 の展開を推進している IT プロフェッショナル、または Microsoft の使用時に政府機関の規制と要件の対象となるデータを処理するその他のエンティティを対象としています。365 Government-GCC はこれらの要件を満たすのに適しています。

> [!NOTE]
> 組織が既に Microsoft 365 Government-GCC の資格要件を満たし、プログラムに受け入れられている場合は、手順1と2をスキップして、手順3に進みます。 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>手順1 組織に Microsoft 365 Government-GCC が必要かどうか、および資格要件を満たしているかどうかを確認します。 

Microsoft 365 Government-GCC 環境は、お客さまのクラウドサービスに関する米国政府の要件に準拠します。これには、FedRAMP の低品質、刑事司法および連邦税情報システム (CJI と FTI のデータ型) が含まれます。

Office 365 の機能を活用できるだけでなく、Microsoft 365 Government-GCC に固有の次の機能を利用することができます。

-   組織の顧客のコンテンツは、Microsoft の一般法人向け Office 365 サービスの顧客のコンテンツから論理的に分離されます。
-   組織の顧客コンテンツは、米国内に保存されています。
-   組織のお客様のコンテンツへのアクセスは、Microsoft のユーザーに制限されています。
-   Microsoft 365 Government-GCC は、米国公的機関のお客様に必要な認定および accreditations に準拠しています。

米国政府機関向け Microsoft 365 政府向けの GCC 製品の詳細については、「[資格要件](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)を含む[Office 365 政府](https://products.office.com/government/compare-office-365-government-plans)機関向けプラン」を参照してください。

[Office 365 US Government service の説明](https://technet.microsoft.com/library/mt774581.aspx)では、プラットフォームの利点について説明します。これは、米国内でのコンプライアンス要件を満たしています。

> [!Tip]
> サービスの説明に記載されている情報の表を Excel ブックに転送して、**組織****のニーズに応じ**て2つの列を追加することができます。 次に、このリストを同僚と確認して、このサービスが組織のニーズを満たしていることを確認します。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断のポイント|<ul><li>組織に対して Microsoft 365 Government-GCC が適切であるかどうかを決定します。</li><li>組織が資格要件を満たしていることを確認します。</li></ul> |

> [!Note]
> Microsoft 365 Government-GCC は米国でのみ利用可能です。 米国政府以外のお客様は、多数の[Office 365 Government プラン](https://products.office.com/en/government/compare-office-365-government-plans)から選ぶことができます。


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>手順2 Microsoft 365 Government-GCC に適用する

このサービスが組織に適していると判断された場合は、[ここでこのサービスの適用](https://products.office.com/government/eligibility-validation)プロセスを開始します。

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>手順3 Microsoft 365 Government-GCC の既定のセキュリティ設定について説明します。

[管理とセキュリティの設定](enable-features-office-365.md)を変更する前に慎重に確認し、コンプライアンスへの影響を考慮して、既定のセキュリティ設定を変更することをお勧めします。

|    |     |
|-----------|------------|
| ![判断ポイントを示すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft 365 Government の既定のセキュリティ設定を変更するかどうかを決定します。解決するには、変更の影響を最初に理解する必要があります。</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>手順4。 現在、どの機能が既定で利用できないか、無効になっているかを理解する。 

政府機関向けクラウドのお客様の要件に対応するため、Microsoft 365 Government-GCC とエンタープライズのプランにはいくつかの違いがあります。 使用できる機能については、次の表を参照してください。

|                             | 機能                     | GCC            |
|-----------------------------|-----------------------------|----------------|
| 技術 | ログイン | 利用可能 |
| | プレゼンス | 利用可能 |
| | 統合されたプレゼンス (Skype for Business および Teams 統合) | 利用可能 |
| 処理 | クロス | 利用可能 |
|  | マイアクティビティ | 利用可能 |
| チャット | チャット | 利用可能 |
| | ファイル | 利用可能 |
| | 組織図 | 利用可能 |
| | 処理 | 利用可能 |
| | 相互運用 (1:1 チーム-Skype for Business チャット) | 利用可能 |
| Teams | チャネルメッセージ | 利用可能 |
| | チャネルファイル | 利用可能 |
| | OneNote タブ | 政府バックログの場合 |
| | チャネルをメールで送信する | 該当なし |
| | メンバーの追加 | 利用可能 |
| | ゲスト アクセス | 利用可能 |
| 会議 | 会議の予約 | 利用可能 |
| | 会議に参加する | 利用可能 |
| | VoIP 会議 | 利用可能 |
| | デスクトップ共有 | 利用可能 |
| | 共有の制御を行う | 利用可能 |
| | 会議室から接続する | 利用可能 |
| | 匿名での参加 | 利用可能 |
| | クラウドの記録 | 利用可能 |
| | 会議のメモ | 利用可能 |
| | ライブ イベント | 利用可能 |
| | フェデレーション会議 | 利用可能 |
| | Surface Hub のサポート | 該当なし |
| 通話 | 連絡先 | 利用可能 |
| | 履歴 | 利用可能 |
| | ボイスメール | 利用可能 |
| | VoIP 通話 | 利用可能 |
| | Skype for ビジネス-チーム通話 | 利用可能 |
| | 通話プラン | 利用可能 |
| | 電話会議 (会議の参加者に PSTN 経由での参加を許可する) | 利用可能 |
| | Microsoft Phone システムのダイレクトルーティング | 利用可能 |
| | PSTN 発信者のロビー | 利用可能 |
| | 通話キュー | 利用可能 |
| | 上司と代理人のサポート | 利用可能 |
| | 提案と安全な移行 | 利用可能 |
| | 飛躍的に応答不可 | 利用可能 |
| | ディスティンクティブリング | 利用可能 |
| | 1:1 を使用して、チーム、Skype for Business、PSTN 参加者とのグループ通話エスカレーション | 利用可能 |
| | グループに転送 | 利用可能 |
| | PSTN 通話に転送 | 利用可能 |
| | 緊急通話-通話プラン | 利用可能 |
| | 既存の認定 SIP 電話のサポート | 利用可能 |
| | USB HID | 利用可能 |
| | 通話と会議の両方の電子情報開示 | 利用可能 |
| | 組織の自動応答 | 利用可能 |
| | Skype コンシューマー-チーム通話サポート | 利用可能 |
| ファイル | 行っ | 利用可能 |
| | Microsoft Teams | 利用可能 |
| ストア | App Store | 政府バックログの場合 |
| 検索 | メッセージ | 利用可能 |
| | ユーザー | 利用可能 |
| | ファイル | 利用可能 |
| | スラッシュコマンド | 利用可能 |
| コン | コンプライアンスコンテンツ検索 | 利用可能 |
| | 保持 | 利用可能 |
| | 監査ログの検索 | 利用可能 |
| | 法的保持 | 利用可能 |
| | 電子情報開示 | 利用可能 |

> [!Note]

> GCC クラウドで他の作業負荷が完全に利用できるようになると、その他の統合作業が完了したときにチームで利用できるようになります。


|    |     |
|-----------|------------|
| ![判断ポイントを示すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Teams 機能セットが組織のニーズを満たすかどうかを決定します。</li></ul> |

## <a name="step-5-plan-for-governance"></a>手順5 ガバナンスの計画

ガバナンスの要件と、それらをどのように満たすかを決定します。 詳細については、「 [Teams のガバナンスの計画」](plan-teams-governance.md)を参照してください。

|    |     |
|-----------|------------|
| ![判断ポイントを示すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>[チームのガバナンス計画](plan-teams-governance.md)のガイドラインに従って、ガバナンス要件を特定して文書化します。</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>手順6 チームをコラボレーションのために展開する

Microsoft 365 Government-GCC に onboarded された後は、 [Fasttrack](https://www.microsoft.com/fasttrack)を使用する標準的な展開方法と、お客様が選んだパートナーを対象に、サービスにオンボードできます。

準備ができたら、チームを展開し[て、チームとチャネルを通じて組織内での共同作業を可能](teams-overview.md)にします。 導入と変更管理チームまたは Teams のエキスパートに相談してください。

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>手順7 会議と音声のチームを展開する

これは、より幅広いステークホルダーグループで Teams を使用して、会議や[クラウド音声機能](cloud-voice-deployment.md)のロールアウトの計画を開始するのに非常に時間がかかることです。

