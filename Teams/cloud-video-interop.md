---
title: Microsoft Teams のクラウド ビデオ相互運用性
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: クラウド ビデオの相互運用機能により、サード ・ パーティ製会議室デバイスをマイクロソフトのチーム会議に参加します。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e038a4618bd456336681c2fff95936a821c770ea
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29742967"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams のクラウド ビデオ相互運用性

クラウド ビデオの相互運用機能により、サード ・ パーティ製会議室デバイスをマイクロソフトのチーム会議に参加します。

コンテンツの共同作業によるテレビ会議、ビデオ会議を最大限に活用するために役立ちます。 ただし、ミーティング ルームのシステムとデバイスは、アップグレードのコストをします。 マイクロソフト チームのクラウド ビデオの相互運用では、システムで動作して、– 会議室またはチーム クライアント内のすべての参加者、ネイティブの会議機能を提供します。 

## <a name="partners-certified-for-microsoft-teams"></a>チームのマイクロソフト認定パートナー

以下のパートナーでは、マイクロソフトのチームのビデオの相互運用機能のソリューションをしています。 会社は、これらのパートナー、企業内の任意の組み合わせを使用することができます。 


|パートナー|パートナー ソリューション|
|----|---|
|![ポリコム RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">ポリコム RealConnect サービス</a> |
|![Pexip 無限大](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">マイクロソフトのチームの Pexip の無限大</a> | 
|![BlueJeans ゲートウェイ](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">マイクロソフトのチームの blueJeans のゲートウェイ</a> |

## <a name="partner-solutions"></a>パートナー ・ ソリューション

パートナーは、マイクロソフトのチーム会議にサード ・ パーティ製の標準ベースの SIP および H.323 のデバイスを接続するゲートウェイ ・ ソリューションを開発しました。  
 
**認定され、マイクロソフトでサポートされています。**

- 認定パートナーのソリューションでのみ使用可能
- マイクロソフトの共同エンジニア リング
- 証明する前にお客様のタップ

**エンタープライズの準備完了**

- HD ビデオ (1080 p) およびコンテンツ (VBSS)
- H.323 および SIP の会議室のデバイスのサポート
- ネイティブ チームおよび交換のスケジュール
- VMR ではなくゲートウェイの設計

**クラウドのスケール**

- Azure を展開しての管理
- クラウド ソリューションの自動サイズ調整

 
## <a name="reference-architecture"></a>リファレンス ・ アーキテクチャ

次の図では、チーム ・ パートナー ・ ソリューションのアーキテクチャの概要について説明します。

![チームのビデオの相互運用をクラウド パートナー ソリューション](media/teams-cloud-video-interop-partner-solution.png)

## <a name="key-business-considerations"></a>重要なビジネス上の考慮事項

**サード パーティ製のビデオ ・ インフラストラクチャとともに、マイクロソフトのチーム**

- サードパーティ製のビデオ デバイスの大規模な展開を持っています。
- 組織でサード パーティ製の呼び出しコント ローラーがあるでしょうか。
- マイクロソフト チームとともに現在、呼び出しのコント ローラーを保持することで計画するか。
- インフラストラクチャに独自のビデオを実行するか、ホストされているでしょうか。 
- チーム ルームのシステムを導入する予定ですか。 いつ。

**相互運用機能プロバイダーを既存の認定**

- 現在、認定パートナーを続行しますか。
- 統合室 (Exchange、1 つのタッチ ダイヤル) のサポートを継続する必要がありますか。

**その他の要件**

- リアルタイムの監視、トラブルシューティング、およびレポート作成機能が必要ですか。
- Sovereign または政府の雲の中で使用できる必要がありますか。
- チーム会議に参加する外部の企業を持っています。 

## <a name="business-workflow-scenarios"></a>ビジネス ワークフロー シナリオ

- **Business Server の Skype-_gt マイクロソフト チーム:** 組織は、サードパーティ製のデバイスと Skype からマイクロソフトのチームへのビジネス prem のサーバーの移動にいます。  
- **オンライン ・ ビジネスの Skype _gt マイクロソフト チーム:** 組織がからに移行するマイクロソフト チーム Skype ビジネスをオンラインにします。
- **Cisco UC の _gt マイクロソフト チーム:** 組織は、マイクロソフトのチームには、Cisco の移動は、Cisco のデバイスを交換する準備ができていません。
- **システムを混在・ _gt マイクロソフト チーム:** 組織は、(Cisco BroadSoft、デバイスのサーバー SfBO) いくつかのシステム、環境内に並べています。
- **会議の別のプロバイダーの _gt マイクロソフト チーム:** 組織は、マイクロソフトのチームに移行するクラウド会議プロバイダーを別のユーザーをされています。


パートナーまたはパートナーを選択すると、[マイクロソフトのチームのクラウド ビデオの相互運用機能を設定](cloud-video-interop-for-teams-set-up.md)する準備ができたら。 
