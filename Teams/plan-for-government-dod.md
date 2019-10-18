---
title: Microsoft 365 米国政府機関向け DoD 展開の計画 - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 米国行政機関の規制の対象となるデータを処理するエンティティで Office 365 の展開を推進するための IT 担当者向けガイダンス。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33495b8a4122df6c0c5d380b835dbfb3a9271eb2
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573297"
---
# <a name="plan-for-microsoft-365-government---dod-deployments"></a>Microsoft 365 Government-DoD の展開計画

このガイダンスは、米国連邦政府機関の法人またはその他の法人で、Microsoft 365 Government – DoD の使用を目的とするデータを処理する IT 365 プロフェッショナルを対象としています。これらの要件を満たしていること。

> [!NOTE]
> 組織が既に Microsoft 365 Government – DoD の資格要件を満たし、プログラムに承認されている場合は、手順1と2をスキップして、手順3に進んでください。

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---dod-and-meets-eligibility-requirements"></a>手順1 組織で Microsoft 365 Government-DoD が必要であるかどうか、および資格要件を満たしているかどうかを確認します。 

Microsoft 365 Government-DoD 環境は、クラウドサービスの米国政府の要件に準拠します。 Office 365 の機能を活用できるように、組織は、Microsoft 365 Government – DoD に固有の次の機能を利用することができます。

- 組織の顧客のコンテンツは、Microsoft の一般法人向け Office 365 サービスの顧客のコンテンツから論理的に分離されます。
- 組織の顧客コンテンツは、米国内に保存されています。
- 組織のお客様のコンテンツへのアクセスは、Microsoft のユーザーに制限されています。
- Microsoft 365 Government – DoD は、米国公的機関のお客様に必要な認定および accreditations に準拠しています。

Microsoft 365 Government –米国政府のお客様向けの詳細については、「[資格の要件](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)を含む[Office 365 政府](https://products.office.com/government/compare-office-365-government-plans)機関向けプラン」を参照してください。

[Office 365 US Government service の説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)では、プラットフォームの利点について説明します。この情報は、米国内での会議のコンプライアンス要件に基づいて中央に配置されています。


> [!Tip]
> サービスの説明に記載されている情報の表を Excel ブックに転送して、**組織****のニーズに応じ**て2つの列を追加することができます。 次に、このリストを同僚と確認して、このサービスが組織のニーズを満たしていることを確認します。


|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断のポイント|<ul><li>組織に対して Microsoft 365 Government-DoD が適切であるかどうかを決定します。</li><li>組織が資格要件を満たしていることを確認します。</li></ul> |

> [!Note]
> Microsoft 365 Government-DoD は、米国でのみ利用可能です。 米国政府以外のお客様は、多数の[Office 365 Government プラン](https://products.office.com/en/government/compare-office-365-government-plans)から選ぶことができます。

## <a name="step-2-apply-for-microsoft-365-government---dod"></a>手順2 Microsoft 365 Government-DoD に適用する

このサービスが組織に適していると判断された場合は、[このサービスの適用](https://products.office.com/government/eligibility-validation)プロセスを開始します。


## <a name="step-3-understand-microsoft-365-government---dod-default-security-settings"></a>手順3 Microsoft 365 Government-DoD の既定のセキュリティ設定について説明します。

[管理とセキュリティの設定](enable-features-office-365.md)を変更する前に慎重に確認し、コンプライアンスへの影響を考慮して、既定のセキュリティ設定を変更することをお勧めします。

|    |     |
|-----------|------------|
| ![判断ポイントを示すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft 365 Government の既定のセキュリティ設定を変更する必要があるかどうかを決定します。解決するには、変更の影響を最初に理解する必要があります。</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---dod"></a>手順4。 Microsoft 365 Government-DoD で現在利用可能な Teams 機能を理解する

政府機関向けクラウドのお客様の要件に対応するために、エンタープライズプランにおける Microsoft 365 Government-DoD と Teams の間には、いくつかの違いがあります。 使用できる機能については、次の表を参照してください。

|                             | 機能                     | 米       |
|-----------------------------|-----------------------------|----------------|
| 技術 | ログイン | 利用可能 |
| | プレゼンス | 利用可能 |
| | 統合されたプレゼンス (Skype for Business および Teams 統合) | 政府バックログの場合 |
| 処理 | クロス | 利用可能 |
|  | マイアクティビティ | 利用可能 |
| チャット | チャット | 利用可能 |
| | ファイル | 利用可能 |
| | 組織図 | 利用可能 |
| | 処理 | 利用可能 |
| | 相互運用 (1:1 チーム-Skype for Business チャット) | 政府バックログの場合 |
| Teams | チャネルメッセージ | 利用可能 |
| | チャネルファイル | 利用可能 |
| | OneNote タブ | 政府バックログの場合 |
| | チャネルをメールで送信する | 該当なし |
| | メンバーの追加 | 利用可能 |
| | ゲスト アクセス | 政府バックログの場合 |
| 会議 | 会議の予約 | 利用可能 |
| | 会議に参加する | 利用可能 |
| | VoIP 会議 | 利用可能 |
| | デスクトップ共有 | 利用可能 |
| | 共有の制御を行う | 利用可能 |
| | 会議室から接続する | 利用可能 |
| | クラウドの記録 | 政府バックログの場合 |
| | 会議のメモ | 利用可能 |
| | ブロードキャスト会議 | 政府バックログの場合 |
| | クラウド内 (DoD から DoD) フェデレーション会議 | 利用可能 |
| | Surface Hub のサポート | 政府バックログの場合 |
| 通話 | 連絡先 | 利用可能 |
| | 履歴 | 利用可能 |
| | ボイスメール | 利用可能 |
| | VoIP 通話 | 利用可能 |
| | Skype for ビジネス-チーム通話 | 利用可能 |
| | 通話プラン | 利用不可 |
| | 電話会議 (会議の参加者に PSTN 経由での参加を許可する) | 利用可能 |
| | Microsoft Phone システムのダイレクトルーティング | 政府バックログの場合 |
| | PSTN 発信者のロビー | 政府バックログの場合 |
| | 通話キュー | 政府バックログの場合 |
| | 上司と代理人のサポート | 政府バックログの場合 |
| | 提案と安全な移行 | 政府バックログの場合 |
| | 飛躍的に応答不可 | 政府バックログの場合 |
| | ディスティンクティブリング | 政府バックログの場合 |
| | 1:1 を使用して、チーム、Skype for Business、PSTN 参加者とのグループ通話エスカレーション | 政府バックログの場合 |
| | グループに転送 | 政府バックログの場合 |
| | PSTN 通話に転送 | 政府バックログの場合 |
| | 緊急通話-通話プラン | 政府バックログの場合 |
| | 既存の認定 SIP 電話のサポート | 政府バックログの場合 |
| | USB HID | 利用可能 |
| | 通話と会議の両方の電子情報開示 | 利用可能 |
| | 組織の自動応答 | 政府バックログの場合 |
| | Skype コンシューマー-チーム通話サポート | 該当なし |
| ファイル | 行っ | 利用可能 |
| | Microsoft Teams | 利用可能 |
| ストア | App Store | 該当なし |
| 検索 | メッセージ | 利用可能 |
| | ユーザー | 利用可能 |
| | ファイル | 利用可能 |
| | スラッシュコマンド | 利用可能 |
| コン | コンプライアンスコンテンツ検索 | 利用可能 |
| | 保持 | 利用可能 |
| | 監査ログの検索 | 利用可能 |
| | 法的保持 | 利用可能 |
| | 電子情報開示 | 利用可能 |

|    |     |
|-----------|------------|
| ![判断ポイントを示すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Teams 機能セットが組織のニーズを満たすかどうかを決定します。</li></ul> |

## <a name="step-5-plan-for-governance"></a>手順5 ガバナンスの計画

ガバナンスの要件と、それらをどのように満たすかを決定します。 詳細については、「 [Teams のガバナンスの計画」](plan-teams-governance.md)を参照してください。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|判断ポイント |<ul><li>[チームのガバナンス計画](plan-teams-governance.md)のガイドラインに従って、ガバナンス要件を特定して文書化します。 </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>手順6 チームをコラボレーションのために展開する

Microsoft 365 Government – DoD に onboarded したら、「 [Microsoft Teams をロールアウトする方法](How-to-roll-out-teams.md)」に記載されている展開の推奨パスに従います。 お客様の導入と変更管理チームやチームのチャンピオンに協力してください。

また、 [Fasttrack](https://www.microsoft.com/fasttrack)または選択したパートナーと連携してサービスを稼働させることもできます。
