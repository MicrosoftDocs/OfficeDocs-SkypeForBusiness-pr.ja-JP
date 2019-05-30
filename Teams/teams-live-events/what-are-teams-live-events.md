---
title: Microsoft Teams のライブ イベントについて
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sonua
search.appverid: MET150
description: ライブイベントを利用して、Microsoft Teams、Yammer、Microsoft Stream の大規模なオンラインの対象ユーザーにビデオとコンテンツをブロードキャストする方法について説明します。
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29537a43fecd2da927497743bc5b488510fbabf7
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548933"
---
# <a name="what-are-microsoft-teams-live-events"></a>Microsoft Teams のライブ イベントについて

## <a name="overview"></a>概要

Microsoft Teams live イベントを使用すると、組織のユーザーは大規模なオンラインユーザーにビデオと会議コンテンツをブロードキャストできます。 

Microsoft 365 ライブイベントは、リアルタイムのビデオストリーミングを新しいレベルで実現し、参加前、ライブ中、ライブイベント後の参加者と、契約のライフサイクル全体を通じて接続を促進します。 Microsoft Stream、Microsoft Teams、または Yammer を使用して、対象ユーザー、チーム、またはコミュニティが置かれている場所で live イベントを作成できます。  

チームは、チャットに基づく共同作業、通話、会議、ライブイベントを提供するため、会議の対象ユーザーを広げることができます。 Teams のライブイベントは、チーム会議の拡張機能であり、ユーザーがビデオや会議コンテンツを大規模なオンライン参加者にブロードキャストできるようにします。 これは、イベントのホストが対話式と参加者の参加につながる1対多の通信を目的としています。主には、ホストによって共有されているコンテンツを表示することになります。 出席者は、Yammer、Teams、または Microsoft Stream でライブまたは記録されたイベントを視聴することができます。また、モデレートされた Q&a または Yammer の会話を使用して、発表者と連絡を取ることができます。 

Teams のライブイベントは、Skype 会議ブロードキャストの次のバージョンと見なされ、最終的には Skype 会議ブロードキャストで提供される機能を置き換えます。 この時点で、Microsoft は組織で Skype for Business を使用しているユーザーのために Skype 会議ブロードキャストを引き続きサポートします。これにより、新規または将来のイベントに対するサービスが中断されることはありません。 ただし、外部のハードウェア/ソフトウェアエンコーダーの画面共有やサポートなど、すべての新機能や魅力的な機能を活用するには、Teams のライブイベントを試すことをお勧めします。 

では、始めましょう。 まず、次の図を見て、Microsoft 365 live イベントに関連する上位コンポーネントとその接続方法について説明します。 

![ライブイベントの主要コンポーネントを示す図](../media/teams-live-events.png  "ライブイベント、スケジュール、生産、Microsoft Stream プラットフォーム、認定されたサードパーティの eCDN プロバイダーの主要コンポーネントを示す図")

### <a name="event-group-roles"></a>イベントグループの役割
Teams のライブイベントにより、複数の役割 (開催者、プロデューサー、発表者、出席者) が正常にブロードキャストされ、イベントに参加できるようになります。 詳細については、「[イベントグループの役割](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles)」を参照してください。

## <a name="key-components"></a>主要コンポーネント
そのため、上の図のように、Teams のライブイベントと共に使用される4つの主なコンポーネントがあります。

### <a name="scheduling"></a>管理
チームは、開催者が適切な出席者権限を持つイベントを作成し、イベントチームメンバーを指定し、運用方法を選択して、出席者を招待する機能を提供します。 ライブイベントが Yammer グループ内で作成された場合、ライブイベントの出席者は、イベントでのユーザーとのやり取りに Yammer の会話を使用できます。 

![[新しいライブイベント] 画面を示すスクリーンショット]新しいライブ(../media/teams-live-events-schedule.png "イベントを作成してスケジュールする新しいライブイベント画面を示すスクリーンショット")

### <a name="production"></a>発行
ビデオ入力はライブイベントの基礎であり、1つの web カメラから複数のカメラの専門ビデオ制作まで、さまざまな場合があります。 Microsoft 365 のライブイベントは、一連の運用シナリオをサポートしており、web カメラを使用するクイックスタートイベント、または外部デバイスやアプリケーションで生成されたイベントを含みます。 プロジェクトの要件と予算に応じて、これらのオプションを選ぶことができます。 イベントを作成するには、次の2つの方法があります。

- **Microsoft teams**: この運用方法では、ユーザーが web カメラを使用して Microsoft Teams でライブイベントを生成したり、チームルームシステムからの A/V 入力を使用したりすることができます。 このオプションは、PC に接続されているオーディオデバイスやビデオデバイスを使用したり、イベントに参加するためにリモートの発表者を招待したりする場合に最も簡単です。 このオプションでは、ユーザーが簡単に web カメラを使用して、画面をイベントに入力として共有できるようにします。 

    ![クイックスタートメソッドを使用して生成されたライブイベントを示すスクリーンショット](../media/teams-live-events-quick-start.png "クイックスタートの運用方法を使用して生成されたライブイベントを示すスクリーンショット")

- **外部アプリケーションまたはデバイス**: 外部エンコーダーを使うと、ユーザーは[Microsoft Stream](https://stream.microsoft.com)を使用して外部ハードウェアまたはソフトウェアベースのエンコーダーから直接ライブイベントを生成できます。 このオプションは、リアルタイムメッセージングプロトコル (RTMP) サービスへのストリーミングをサポートする、studio 品質機器 (メディアミキサーなど) を既にお持ちの場合に最適です。 通常、この種類の生産は、役員のような大きなイベント (メディアミキサーの1つのストリームが対象ユーザーにブロードキャスト) で使用されます。 

    ![外部エンコーダーを使用して生成されたライブイベントを示すスクリーンショット](../media/teams-live-events-external-encoder.png "外部エンコーダーの運用方法を使用して生成されたライブイベントを示すスクリーンショット")

### <a name="streaming-platform"></a>ストリーミングプラットフォーム
ライブイベントストリーミングプラットフォームは、次の要素で構成されています。

- **Azure**media services: [azure media services](https://docs.microsoft.com/azure/media-services/previous/)では、最も人気の高いモバイルデバイスで、ブロードキャスト品質のビデオストリーミングサービスを利用して、多くのユーザーに連絡できます。 メディアサービスは、ユーザー補助機能、配布、スケーラビリティを強化し、コンテンツを保護しながら、ローカルまたは世界中の対象ユーザーにコンテンツをストリーミングするための簡単で費用の高い機能を実現します。
- **Azure コンテンツ配信ネットワーク (cdn)**: ストリームがアクティブになると、 [Azure コンテンツ配信ネットワーク (cdn)](https://docs.microsoft.com/azure/cdn/)を通じて配信されます。 Azure Media Services には、ストリーミングエンドポイント用の統合 CDN が用意されています。 これにより、ストリームはバッファリングせずに世界中で表示することができます。

### <a name="enterprise-content-delivery-network-ecdn"></a>エンタープライズコンテンツ配信ネットワーク (eCDN)
ECDN の目標は、インターネット上のビデオコンテンツを取得し、ネットワークのパフォーマンスに影響を及ぼすことなく、企業全体にコンテンツを配布することです。 次の認定された eCDN パートナーのいずれかを使用して、組織内で保持されるライブイベントのネットワークを最適化することができます。
- [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](http://www.kollective.com)
- [見本](http://www.ramp.com)

### <a name="attendee-experience"></a>出席者の操作 
出席者のエクスペリエンスは、ライブイベントの最も重要な側面であり、出席者が問題を発生させることなくライブイベントに参加できるようにすることが重要です。 出席者のエクスペリエンスでは、Azure Media Player (Microsoft Teams で作成されたイベント用) と Stream Player (外部暗号化によって生成されたイベントの場合) は、デスクトップ、ブラウザー、モバイル (iOS、Android) で動作します。 Office 365 では、Yammer と Teams が2つのコラボレーションハブとして提供され、live 参加者エクスペリエンスはこれらのコラボレーションツールに統合されています。 

![ライブイベントの出席者エクスペリエンスを示すスクリーンショット](../media/teams-live-events-attendee.png "ライブイベントの出席者エクスペリエンスを示すスクリーンショット")

## <a name="next-steps"></a>次のステップ
「 [Teams ライブイベントのプラン](plan-for-teams-live-events.md)」に移動します。

### <a name="related-topics"></a>関連トピック
- [Yammer、Microsoft Teams、Microsoft Stream の Microsoft 365 全体でのライブイベント](https://docs.microsoft.com/stream/live-event-m365)
- [Microsoft Teams でのライブイベント](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Yammer のライブイベント](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Microsoft Stream のライブイベント](https://docs.microsoft.com/stream/live-event-overview)

 
