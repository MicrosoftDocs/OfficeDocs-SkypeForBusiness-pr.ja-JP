---
title: "Microsoft Teams 用に組織のネットワークを準備する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "ネットワーク要件、帯域幅要件、その他の考慮事項といった Microsoft Teams ネットワークの準備と管理について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 399a0a6ed6ac5bfabeac97f41e82e0237bca0b74
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2017
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a>Microsoft Teams 用に組織のネットワークを準備する
=================================================

Microsoft Teams は 3 つの形態のトラフィックを組み合わせて使用します。

-   Office 365 オンライン環境と Microsoft Teams クライアント間のデータ トラフィック (信号、プレゼンス、チャット、ファイルのアップロードとダウンロード、OneNote 同期)。

-   ピアツーピアのリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。

-   会議型のリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。

この組み合わせは 2 つのレベルにおけるネットワークに対して影響を及ぼします。ピアツーピアの場合、トラフィックは Microsoft Teams クライアント間で直接にフローします。会議のシナリオの場合、トラフィックは Office 365 環境と Microsoft Teams クライアント間をフローします。最適なトラフィック フローを実現するには、内部ネットワーク セグメント間 (WAN 上でのサイト間) のフロー、さらにネットワーク サイトと Office 365 間のフローの両方を許可する必要があります。適切なポートを開かなかったり、特定のポートを自動的に遮断すると、ネットワーク エクスペリエンスの質が低下します。

|  |  |
|---------|---------|
|![重要アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image1.png)<br></br>重要    |現在、iOS と Android モバイル デバイスでは会議がサポートされていますが、Windows Phone ではサポートされていません (Windows Phone でのサポートは準備中です)。       |

Microsoft Teams でリアルタイム メディアの最適な操作性を実現するには、Office 365 のネットワーク要件を満たす必要があります (詳しくは、「[Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917?ui=en-US&rs=en-US&ad=US)」をご覧ください)。

次の 2 つの重要なネットワーク セグメント (クライアントから Microsoft Edge、Customer Edge から Microsoft Edge) は、以下の要件を満たす必要があります。


|値  |クライアントから Microsoft Edge  |Customer Edge から Microsoft Edge  |
|---------|---------|---------|
|**遅延 (一方向)**     |< 50 ミリ秒          |< 30 ミリ秒          |
|**遅延 (RTT または往復時間)** |< 100 ミリ秒         |< 60 ミリ秒         |
|**バースト パケット損失**    |< 任意の 200 ミリ秒間隔で 10%         |< 任意の 200 ミリ秒間隔で 1%         |
|**パケット損失**     |< 任意の 15 秒間隔で 1%          |< 任意の 15 秒間隔で 0.1%         |
|**パケット到着間ジッター**    |< 15 秒間隔で 30 ミリ秒         |< 任意の 15 秒間隔で 15 ミリ秒         |
|**パケットの並べ替え**    |< 順序が適切でないパケットが 0.05%         |< 順序が適切でないパケットが 0.01%         |

これらのネットワーク セグメントの両方をテストするには、Network Assessment Tool を使用できます (提供元: [https://www.microsoft.com/en-us/download/details.aspx?id=53885](https://go.microsoft.com/fwlink/?linkid=855799))。このツールは、クライアント PC で直接展開するか、Customer Network Edge に接続された PC/ラップトップで展開できます。このツールには簡易的なマニュアルが含まれています。このツールの使用法について詳細なマニュアルについては、[Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800) にアクセスしてください。この Network Readiness Assessment を実行すると、Microsoft Teams などのリアルタイム アプリケーションの実行に対するネットワークの準備を検証できます。

|  |  |
|---------|---------|
|![注意アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image2.png)<br></br>注意    |これは Skype for Business を展開するカスタマ向けに推奨される Network Readiness Assessment と同じです。         |

<a name="bandwidth-requirements"></a>帯域幅要件
----------

Microsoft Teams の帯域幅の計算は複雑であるため、それを支援する計算ツールが用意されています。この計算ツールにアクセスするには、<http://aka.ms/bwcalc/> に移動してください。

以下の内容は、付属的な背景情報として利用できます。ただし、[帯域幅計算ツール](https://aka.ms/bwcalc) を使用して必要な項目を追跡する場合は、推奨事項として参考にしてください。

|  |  |
|---------|---------|
|![注意アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image2.png)<br></br>注意    |必要とされる帯域幅が利用できない場合は、Microsoft Teams 内部のメディア スタックにより、利用可能な帯域幅の不足量を補うため音声/ビデオ セッションの品質が低下し、その結果、通話や会議の品質も影響を受けます。Microsoft Teams クライアントはビデオの品質よりもオーディオの品質を優先します。したがって、必要とされる帯域幅を利用可能な状態にすることが非常に重要になります。       |


|アクティビティ  |ダウンロードの帯域幅  |アップロードの帯域幅  |トラフィック フロー |
|---------|---------|---------|---------|
|**ピアツーピア音声通話**     |0.1 Mb         |0.1Mb         |クライアント <> クライアント         |
|**ピアツーピア ビデオ通話 (全画面)**     |4 Mb         |4Mb         |クライアント <> クライアント          |
|**ピアツーピア デスクトップ共有 (1920*1080 解像度)**     |4 Mb         |4 Mb         |クライアント <> クライアント          |
|**2 人が参加する会議**     |4 Mb         |4 Mb         |クライアント <> Office 365         |
|**3 人が参加する会議**     |8 Mb         |6.5 Mb         |クライアント <> Office 365           |
|**4 人が参加する会議**     |5.5 Mb         |4 Mb         |クライアント <> Office 365           |
|**5 人以上が参加する会議**     |6 Mb         |1.5 Mb         |クライアント <> Office 365           |


<a name="additional-network-considerations"></a>ネットワークに関する追加の考慮事項
---------------

#### <a name="external-name-resolution"></a>**外部の名前解決**

Microsoft Teams を実行するすべてのクライアント コンピュータが外部 DNS クエリを解決して、Office 365 によって提供されるサービスを検出できることを確認してください。

#### <a name="nat-pool-size"></a>**NAT プール サイズ**

複数のユーザーまたはデバイスがネットワーク アドレス変換 (NAT) またはポート アドレス変換 (PAT) を使用して Office 365 にアクセスする場合は、パブリック ルーティング可能な各 IP アドレスの後ろに隠れているデバイスが、サポートされる数値を超過していないことを確認する必要があります。

このリスクを軽減するには、適切なパブリック IP アドレスを NAT プールに割り当ててポート枯渇を回避します。ポート枯渇は、Office 365 サービスに接続するときに発生するエンドユーザーやデバイスの問題の原因となります。詳しくは、「[Office 365 の NAT サポート](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)」ガイドをご覧ください。

#### <a name="intrusion-detection-and-prevention-guidance"></a>**侵入検知/防御のガイダンス**

送信接続の追加のセキュリティ レイヤとして環境に侵入検知/防御システム (IDS/IPS) が配備されている場合は、送信先から Office 365 URL へのトラフィックがホワイトリストに記載されていることを確認してください。

<a name="network-health-determination"></a>ネットワーク正常性の確認
-----------------

ネットワーク内で Microsoft Teams を実装する計画を行う場合は、必要とされる帯域幅とすべての必須 IP アドレスへのアクセスが確保されていること、正しいポートが開かれていること、リアルタイム メディアのパフォーマンス要件を満たしていることを確認する必要があります。

これらの条件を満たすことができない場合は通話や会議中の品質が悪くなるため、エンドユーザーは Microsoft Teams の最適なエクスペリエンスを得ることができません。

これらの要件を満たしていない場合は、先に進む前にプロジェクトを中断して、条件を満たすことをお勧めします。


|  |  |  |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |判断ポイント         |リアルタイム メディアをサポートするためにネットワーク能力を評価したことはありますか?<br></br>ネットワークが正しく評価されていない場合やリアルタイム メディアをサポートできないことが事前に分かっている場合は、ビデオや画面共有の機能を無効にして、ネットワークへの影響を軽減し、Teams エクスペリエンスの質を向上させることができます。         |
|![次のステップ アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |次のステップ         |ネットワークの品質が不明な場合: skypeoperationsframework.com で入手できる Network Readiness Assessment のガイダンスに従って、お客様のネットワークでリアルタイム メディアに対する準備が整っているかどうかを判別してください。<br></br>ネットワークの品質が乏しい場合: ネットワーク改善の手順を実行して、高品質なリアルタイム メディアに適した環境を整えてください。<br></br>十分なネットワーク品質: すべての IP アドレスやポートに正しくアクセスできることを確認してください。           |

