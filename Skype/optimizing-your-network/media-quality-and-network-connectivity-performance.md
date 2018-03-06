---
title: "Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/21/2016
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
description: "このトピックでは、Skype for Business Online サービスの一連のネットワーク パフォーマンス要件を定義し、ネットワーク接続のアセスメントに基づいて、ネットワークと Skype for Business Online の接続にインターネットと ExpressRoute のどちらを使用するかを選択する方法を説明します。 Office 365 への専用接続用に Azure ExpressRoute を展開することにした場合、このドキュメントでは、Skype for Business Online 展開のさまざまなシナリオで ExpressRoute 接続を計画する方法についても説明します。"
---

# Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス

このトピックでは、Skype for Business Online サービスの一連のネットワーク パフォーマンス要件を定義し、ネットワーク接続のアセスメントに基づいて、ネットワークと Skype for Business Online の接続にインターネットと ExpressRoute のどちらを使用するかを選択する方法を説明します。 Office 365 への専用接続用に Azure ExpressRoute を展開することにした場合、このドキュメントでは、Skype for Business Online 展開のさまざまなシナリオで ExpressRoute 接続を計画する方法についても説明します。
  
IP 上のリアルタイム メディア (オーディオ、ビデオ、アプリケーション共有など) の品質は、エンド ツー エンドのネットワーク接続の品質に大きく影響されます。 Skype for Business Online メディアの最適な品質を得るために、会社のネットワークと Skype for Business Online 間の接続が高品質であることを確認するのは重要です。 これを達成する最善の方法は、内部ネットワークとクラウド接続を、接続全体にわたって Skype for Business Online のピーク時のトラフィック量を処理するネットワークのキャパシティに基づいて設定することです。
  
Azure ExpressRoute は、Skype for Business Online を含む Office 365 サービスの要件ではありません。 ただし、Azure ExpressRoute は利用可能な展開オプションの 1 つで、Office 365 への接続が Skype for Business ネットワーク パフォーマンス要件を満たすことに役立ち、Skype for Business Online の最適なメディア品質エクスペリエンスを実現できるようにします。
  
> [!TIP]
> このトピックではネットワーク パフォーマンスの全体的なガイダンスを説明しますが、ネットワーク アセスメントの完全なガイダンスはこのドキュメントの範囲外です。全体的かつ完全なネットワーク アセスメントの一部としてネットワーク パフォーマンス測定を支援できる Skype for Business Online パートナーのリストは、「[Skype for Business パートナー ソリューション](http://partnersolutions.skypeforbusiness.com/)」を参照してください。 
  
## Skype for Business Online のネットワーク接続要件

### Skype for Business Online メディア品質に影響する要因

使用するデバイス、環境、ネットワーク接続などを含む、Skype for Business Online リアルタイム メディア (オーディオ、ビデオ、アプリケーション共有など) の品質に関わる要因は数多くあります。 
  
#### デバイス

リアルタイム メディア セッションでは、ヘッドセットや Web カメラなどの参加者全員が使用するメディアのキャプチャ デバイスやレンダリング デバイスは、オーディオとビデオの全体的な品質に大きく影響します。 品質の低いデバイスや、デバイス ドライバが間違っているデバイスでは、全体的にオーディオの音質が下がり、ビデオの画質が下がります。 一方、認定デバイスまたは高品質なデバイスは、エコー キャンセル、ノイズ フィルタリング、ビデオ解像度、遅延低減に役立ちます。
  
とはいえ、オーディオやビデオの認定メディア デバイスが必要というわけではありません。それは、最適なメディア エクスペリエンスを実現するために Skype for Business 向けに認定された、強く推奨されるデバイスです。すべての Skype for Business 認定デバイスのリストについては、「[Skype for Business の電話とデバイス](https://technet.microsoft.com/en-us/office/dn947482)」を参照してください。 **Skype for Business 管理センター** にある[ Skype for Business Online 通話品質ダッシュボード](https://support.office.com/en-us/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c?ui=en-US&amp;rs=en-US&amp;ad=US)を使用して、使用中のデバイスが正しく動作していることを確認し、オーディオとビデオのメディア品質を監視することができます。
  
> [!TIP]
> **Skype for Business で最適なメディア品質を得るには、認定デバイスが必要です** 。
  
リアルタイム メディアが流れるどのメディア デバイス、Skype for Business クライアント、Skype for Business Servers でも、ある程度の遅延が発生することを覚えておくのは重要です。 ネットワーク遅延と併せて、遅延を処理するデバイスとソフトウェアは、エンド ツー エンドの全体的な遅延やエンド ユーザーのエクスペリエンスに大きく影響します。
  
#### 環境

ユーザーが会議を行い、オーディオ デバイスとビデオ デバイスを使用する環境と周辺領域は、オーディオとビデオの品質のもう 1 つの要因です。 ノイズのある環境から通話しているユーザーのオーディオは、エコーがかかり、こもっていて、不明瞭です。 暗くて照明が不十分な環境にいるユーザーは、ビデオで明るくクリアな画質を実現することができません。 会議室の設定で、マイクとビデオ デバイスの場所は、参加者が受信する音声と画像の品質に直接影響します。
  
ユーザーがオーディオとビデオでよりクリアな画像を得るには、Skype for Business アプリケーションで、[ **ツール**] > [ **オプション**] > [ **オーディオ デバイス**] または [ **ビデオ デバイス**] を使用して、使用中のデバイスを変更し、その設定をカスタマイズします。また、[ **通話品質の確認**] をクリックして、通話のオーディオ品質を確認することができます。[ **通話品質の確認**] をクリックすると、テスト呼び出しで確認された品質と問題が報告されます。
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### ネットワーク

IP ネットワーク上のリアルタイム メディアの品質は、ネットワーク接続の品質、特に以下の量に大きく影響されます。
  
- **遅延** これは、ネットワーク上の A 地点から B 地点に IP パケットを転送するのにかかる時間です。このネットワーク伝達遅延は基本的に、中間に存在するさまざまなルーターによって発生する追加のオーバーヘッドを含む、2 地点間の物理的な距離および光の速度に結びついています。遅延は、一方向または往復時間 (RTT) で測定されます。
    
- **パケット損失** これは多くの場合、特定の時間枠に失われたパケットの割合で定義されます。パケット損失は、ほとんど影響のない小規模な個々の損失パケットから、オーディオが完全に途切れる連続した急激な損失まで、オーディオ品質に直接影響します。
    
- **パケット間到着ジッターまたは単純ジッター** これは、連続するパケット間における遅延での平均的な変更です。Skype for Business を含む最新の VoIP ソフトウェアは、バッファを介して一定レベルのジッターに適応することができます。これは、ジッターがバッファを超えて参加者がジッターの影響に気づく場合のみです。
    
> [!NOTE]
> ジッターのバッファリングにより、エンド ツー エンドの遅延が増えます。 
  
他の Office 365 サービスや他のビジネス アプリケーションで生成される別のネットワーク トラフィックに加えて、Skype for Business Online リアルタイム メディア セッションを数多く同時に行う場合は、ネットワークの混雑を防ぎ、優れたメディア リアルタイム メディア (オーディオ、ビデオ、アプリケーション共有など) 品質を得るために、使用するネットワークと Skype for Business Online を接続するネットワーク パス全体に十分な帯域幅があることを確認することが重要です。 
  
#### 混雑したネットワーク全体でサービスの品質 (QoS) を実装する

さらに、ネットワーク全体にわたってトラフィックが混雑していると、メディア品質に大きく影響します。 オーディオとビデオのパケットがネットワークをすばやく通過して、混雑したネットワーク上で他のネットワーク トラフィックよりも優先されるようにするには、サービスの品質 (QoS) を使用してオーディオとビデオの通信で最適なエンド ユーザー エクスペリエンスを提供できるようにすることができます。
  
QoS を使用すると、オーディオやビデオのデータを運ぶネットワーク パケットに、より高い優先順位を割り当てることができます。 これらのパケットにより高い優先順位を割り当てると、オーディオとビデオの通信は、ファイル転送、Web の参照、またはデータベースのバックアップなどを行うネットワーク セッションよりも、ネットワーク上をより速く、より少ない中断で移動するようになります。 これは、ファイル転送やデータベースのバックアップに既定で使用するネットワーク パケットには優先順位として「ベスト エフォート」が割り当てられており、ネットワーク混雑の影響が大きくないためです。 メディア (オーディオ、ビデオ、アプリケーション共有など) パケットに高い優先順位を割り当てず、「ベスト エフォート」を割り当てたままにした場合は、その他すべてのネットワーク トラフィックと一緒に処理されます。 ネットワークの混雑度によっては、これによりオーディオ品質やビデオ品質がユーザーにとって全体的に不満足なものとなる可能性があります。
  
ネットワーク上で QoS を実装し、ネットワーク内の混雑による影響をなくすことが強く推奨されます。ただし、最大の効果を上げるには、すべてのネットワーク エンドポイントで QoS をサポートする必要があります。つまり、すべてのエンドポイントが QoS マーキングやパケット優先順位を守る必要があるということです。Skype for Business Online サービスは、Microsoft ネットワーク内の QoS マーキングおよび優先順位を守ります。ただし、会社のネットワークから Microsoft ネットワークへのインターネットなどのパブリック接続を介してルーティングされたトラフィックは、QoS マーキングやパケット優先順位を保持しません。[Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) を使用したネットワークから Office 365 へのプライベート接続では、QoS マーキングやパケット優先順位を保持する展開ソリューションが提供されますが、その結果エンド ユーザーにとって、オーディオとビデオの全体的な品質が向上します。
  
## Skype for Business Online に接続するためのネットワーク パフォーマンス要件
<a name="bk_NetworkPerf"> </a>

Skype for Business リアルタイム メディアは、さまざまなネットワークにわたる、さまざまなデバイス、クライアント アプリケーション、サーバ ソフトウェアなどを通過します。 リアルタイム メディアのエンド ツー エンド遅延は、すべてのコンポーネントおよびネットワーク セグメントにわたって発生する遅延の総量です。 エンド ツー エンド ネットワーク接続の品質は、最低の品質を持つネットワーク セグメントによって決まります。 このセグメントは、このネットワーク トラフィックのボトルネックとして機能します。
  
以下の図は、電話会議における Skype for Business のある参加者から別の参加者への一方向のオーディオ フローを示しています。
  
![ExpressRoute Call Flow.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
この会議シナリオで、メディア パスは以下のネットワーク セグメント全体に存在します。
  
1. **ユーザー 1 から Microsoft ネットワークのエッジへの接続** これには通常、WiFi やイーサネットなどのネットワーク接続、ユーザー 1 からインターネットの出口ポイント (ネットワーク エッジ デバイス) への WAN 接続、およびネットワーク エッジから Microsoft ネットワーク エッジへのインターネット接続などが含まれます。
    
2. **Microsoft ネットワーク内の接続** これは、Microsoft Edge と Skype for Business Online データ センター間で、A/V 会議サーバが使用されます。
    
3. **Microsoft ネットワーク内の接続** これは、Skype for Business Online データ センターと Microsoft ネットワーク エッジ間です。
    
4. **Microsoft ネットワーク エッジからユーザー 2 への接続** これには、ネットワーク エッジから Microsoft ネットワーク エッジへのインターネット接続、ユーザー 2 からインターネット出口ポイント (ネットワーク エッジ) への WAN 接続、Wifi やイーサネットなどのネットワーク接続などが含まれます。
    
以下の図は、Skype for Business Online PSTN 通話のコンポーネントやネットワーク セグメントの詳細を示しています。
  
![ExpressRoute PSTN Carrier Call Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
PSTN 通話シナリオにおいて、メディア パスは以下のネットワーク セグメントを横断します。
  
1. **Skype for Business クライアントの発信者から Microsoft ネットワーク エッジへの接続** これには通常、WiFi やイーサネット、Skype for Business クライアントの発信者からインターネットの出口ポイント (ネットワーク エッジ デバイス) への WAN 接続、およびネットワーク エッジから Microsoft ネットワーク エッジへのインターネット接続などが含まれます。
    
2. **Microsoft ネットワーク内の接続** これは、Microsoft Edge と Skype for Business Online データ センター間で、仲介サーバーが使用されます。
    
3. **Microsoft ネットワーク内の接続** これは、Skype for Business Online データ センターと Microsoft ネットワーク エッジ間です。
    
4. **Microsoft ネットワークと PSTN サービス プロバイダー パートナー間の接続** これは、Microsoft ネットワーク外の Skype for Business クライアントから PSTN 通話を発信するために存在する接続です。
    
### Skype for Business クライアントから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件
<a name="bk_SfBClienttoEdge"> </a>

Skype for Business で最適なメディア品質を得るには、会社のネットワークから Microsoft ネットワーク エッジへの接続で、以下のネットワーク パフォーマンス指標のターゲットまたはしきい値が必要です。 ネットワークのこのセグメントには内部ネットワークが含まれ、これにはすべての WiFi およびイーサネット接続、Multiprotocol Label Switching (MPLS) などの WAN 接続を介した会社のあらゆるサイト間トラフィック、Microsoft ネットワーク エッジへのインターネットまたは ExpressRoute パートナー接続が含まれます。
  
> [!CAUTION]
> **会社のネットワークの Skype for Business クライアントと Office 365 サービス間の接続は、以下のネットワーク パフォーマンス要件としきい値を満たす必要があります。**
  
|||
|:-----|:-----|
|**メトリック** <br/> |**ターゲット** <br/> |
|遅延 (一方向)  <br/> |< 50 ミリ秒  <br/> |
|遅延 (RTT または往復時間)  <br/> |< 100 ミリ秒  <br/> |
|バースト パケット損失  <br/> |< 任意の 200 ミリ秒間隔で 10%  <br/> |
|[パケット損失]  <br/> |< 任意の 15 秒間隔で 1%  <br/> |
|パケット到着間ジッター  <br/> |< 15 秒間隔で 30 ミリ秒  <br/> |
|パケットの並べ替え  <br/> |< 順序が適切でないパケットが 0.05%  <br/> |
   
 **その他のパフォーマンス ターゲット要件:**
  
- Microsoft ネットワークには、世界中で 160 を超えるエッジの場所があります。 これらのエッジ サイトを介して世界中の主なインターネット サービス プロバイダー (ISP) と連携しています。 遅延メトリック ターゲットは、会社のサイトと Microsoft Edge が同じ大陸にあることを前提としています。
    
- 会社のサイトから Microsoft ネットワーク エッジへの接続には、最初のホップのネットワーク アクセスが含まれます。これは、WiFi や別のワイヤレス テクノロジである可能性があります。 
    
- ネットワーク パフォーマンス ターゲットは、帯域幅やサービスの品質が適切に計画されていることを前提としています。 言い換えると、ネットワーク接続の負荷がピークに達している場合に、これが Skype for Business リアルタイム メディア トラフィックに直接適用されます。
    
### ネットワーク エッジから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件
<a name="bk_YourNetworkEdge"> </a>

以下は、ネットワーク エッジと Microsoft ネットワーク エッジ間の接続に必要なネットワーク パフォーマンス ターゲットまたはしきい値です。 ネットワークのこのセグメントでは、お客様の内部ネットワークや WAN が除外されます。これは、インターネットまたは ExpressRoute パートナー ネットワークを介して送信されるネットワーク トラフィックをテストする場合のガイダンスとして使用することを目的としており、また ExpressRoute プロバイダーとパフォーマンス サービス レベル アグリーメント (SLA) を交渉する場合に使用することもできます。
  
> [!CAUTION]
> **会社のネットワーク エッジと Microsoft ネットワーク エッジ間の接続は、以下のネットワーク パフォーマンス要件としきい値を満たす必要があります。**
  
|||
|:-----|:-----|
|**メトリック** <br/> |**ターゲット** <br/> |
|遅延 (一方向)  <br/> |< 30 ミリ秒  <br/> |
|遅延 (RTT)  <br/> |< 60 ミリ秒  <br/> |
|バースト パケット損失  <br/> |< 任意の 200 ミリ秒間隔で 1%  <br/> |
|[パケット損失]  <br/> |< 任意の 15 秒間隔で 0.1%  <br/> |
|パケット到着間ジッター  <br/> |< 任意の 15 秒間隔で 15 ミリ秒  <br/> |
|パケットの並べ替え  <br/> |< 順序が適切でないパケットが 0.01%  <br/> |
   
 **その他のパフォーマンス ターゲット要件:**
  
- パフォーマンス ターゲットでは、会社のいずれかのネットワーク エッジとその最寄の Microsoft ネットワーク エッジ間の接続が同じ大陸にあることが必要です。
    
- ネットワーク パフォーマンス ターゲットでは、帯域幅やサービスの品質が適切に計画されていることを前提としています。ネットワーク接続の負荷がピークに達している場合に、これが Skype for Business リアルタイム メディア トラフィックにも適用されます。適切な帯域幅と QoS の計画については、「[Skype for Business Online の ExpressRoute および QoS](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US)」を参照してください。
    
## ネットワーク パフォーマンスの測定
<a name="bk_NetworkPerf"> </a>

会社のネットワーク サイトからネットワーク エッジへの実際のネットワーク パフォーマンス、特に遅延とパケット損失を測定するには、ping、PSPing、tcping などのツールを使用して、Microsoft Edge およびデータ センター サイトから実行している一連の Skype for Business メディア リレー サービスをテストすることができます。 
  
Microsoft ネットワークへのインターネット接続をテストするには、Skype for Business メディア リレーの以下の VIP をテストすることをお勧めします。 *Anycast VIP*  は、テストの場所に最も近い Microsoft Edge サイトのメディア リレーの IP アドレスに解決されます。
  
||||
|:-----|:-----|:-----|
|**IP アドレス** <br/> |**種類** <br/> |**場所** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |世界の Anycast IP  <br/> |
   
 **ネットワーク パフォーマンスのアセスメントで従う高レベルの推奨事項を以下に示します。**
  
- 内部ネットワークに加えて Office 365 への接続のアセスメントも行う必要があります。
    
- 長期間にわたってすべてのネットワークのデータを収集してアセスメントを行う必要があります。 ネットワーク パフォーマンスのテストは最低でも 1 週間にわたって行うことをお勧めします。そうすると、すべての営業日および営業時間の使用状況のパターンがわかります。 これによりピーク時がわかります。
    
- ネットワーク パフォーマンス測定の複数のサンプルを取る必要があります。 データを収集している期間全体にわたって、会社のサイトから 10 分ごとに測定を行うことをお勧めします。 Skype for Business Online ネットワーク パフォーマンス要件を比較するには、このサンプル データ セットから 90 パーセント目にあたる値を取ります。 
    
- ネットワークのパフォーマンスのアセスメントは継続的に行う必要があります。 使用パターンの変化、帯域幅を大幅に消費するエンタープライズ ベースの新しいアプリケーション、組織の変更や会社の物理的な移転などが原因で、ネットワーク使用率は時間の経過とともに変わります。 これらのネットワーク パフォーマンス要件およびターゲット/しきい値についてネットワーク パフォーマンスを継続的に監視すること、および最適なリアルタイム メディア品質を得るためにタイムリーに調整することは重要です。 
    
## Azure VM を使ったネットワーク パフォーマンスの測定
<a name="bk_NetworkPerf"> </a>

Microsoft ネットワークの Edge サイトに対するテストを行う代わりに、Microsoft Azure クラウド内のサービスのためのセットアップのテストを活用する、Skype for Business の顧客およびパートナーによるネットワーク アセスメントのソリューションが存在します。 これらのソリューションでは、ネットワーク アセスメント ツールが Azure クラウド内のサービスとしてのカスタム エンドポイントのセットアップに対して遅延、パケット損失、ジッターについてテストします。 結果として、テストのネットワーク トラフィックは 1 つの追加ネットワーク セグメントにわたって通過します。このネットワーク セグメントは、ネットワーク アセスメント サービスをホストする Microsoft ネットワーク内のネットワーク エッジと Azure データセンターとの間の接続になります。
  
これらのネットワーク アセスメント ソリューションについては、Azure のホストされたテスティング サービスに基づきます。 国内または地域内でネットワーク アセスメントを実行することを推奨します。 たとえば、顧客のサイトがアメリカ東部の場合、アセスメントは、Azure のアメリカ東部のデータセンター地域にホストされたテスティング サービスのインスタンスに対して実行する必要があります。 
  
ネットワーク アセスメントのセットアップに基づいた Azure サービスの遅延 (RTT) ターゲットは以下のとおりです。 一方向の遅延ターゲットは、対応する RTT ターゲットの半分になります。 パケット損失とジッターは、Skype のメディア リレーに基づくテスティングで定義されたものと変わらないままです。
  
|||||
|:-----|:-----|:-----|:-----|
|**顧客の地域** <br/> |**Azure の地域** <br/> |**ネットワークのエッジ - Azure 間のラウンドトリップ時間 (RTT)** <br/> |**サイト - Azure 間のラウンドトリップ時間 (RTT)** <br/> |
|米国中央部  <br/> |米国中央部  <br/> |99  <br/> |139  <br/> |
|米国東部  <br/> |米国東部  <br/> |86  <br/> |126  <br/> |
|米国中北部  <br/> |米国中北部  <br/> |97  <br/> |137  <br/> |
|米国中南部  <br/> |米国中南部  <br/> |94  <br/> |134  <br/> |
|米国西部  <br/> |米国西部  <br/> |94  <br/> |134  <br/> |
|米国ハワイ  <br/> |米国西部  <br/> |116  <br/> |156  <br/> |
|カナダ中部  <br/> |カナダ中部  <br/> |138  <br/> |178  <br/> |
|カナダ東部  <br/> |カナダ東部  <br/> |131  <br/> |171  <br/> |
|北ヨーロッパ  <br/> |北ヨーロッパ  <br/> |99  <br/> |139  <br/> |
|西ヨーロッパ  <br/> |西ヨーロッパ  <br/> |95  <br/> |135  <br/> |
|東アジア  <br/> |東アジア  <br/> |118  <br/> |158  <br/> |
|東南アジア  <br/> |東南アジア  <br/> |97  <br/> |137  <br/> |
|東日本  <br/> |東日本  <br/> |111  <br/> |151  <br/> |
|西日本  <br/> |西日本  <br/> |118  <br/> |158  <br/> |
|ブラジル南部  <br/> |ブラジル南部  <br/> |70  <br/> |110  <br/> |
|オーストラリア東部  <br/> |オーストラリア東部  <br/> |124  <br/> |164  <br/> |
|オーストラリア南東部  <br/> |オーストラリア南東部  <br/> |124  <br/> |164  <br/> |
|インド中央部  <br/> |インド中央部  <br/> |103  <br/> |143  <br/> |
|インド南部  <br/> |インド南部  <br/> |103  <br/> |143  <br/> |
|インド西部  <br/> |インド西部  <br/> |103  <br/> |143  <br/> |
|中国東部  <br/> |中国東部  <br/> |120  <br/> |160  <br/> |
|中国北部  <br/> |中国北部  <br/> |120  <br/> |160  <br/> |
   
## メディア品質と ExpressRoute
<a name="bk_NetworkPerf"> </a>

Azure ExpressRoute for Office 365 は、Office 365 に接続する専用ネットワーク接続です。 これにより、Office 365 ネットワーク トラフィックが使用するパスを制御する機能が提供されます。 不明なキャリア、プロバイダー、ISP などによってデータが運ばれるインターネットで発生する、予測できないルーティングを懸念する必要がなくなります。 ExpressRoute を介して送信されるネットワーク トラフィックは、ExpressRoute パートナーのネットワーク全体から直接 Microsoft のネットワークに送信されます。 これにより、Office 365 が専用接続を使用して自社のオフサイト データ センターに存在するかのように扱うことができます。
  
Azure ExpressRoute は、すべての Office 365 ライセンス製品で使用できます。ただし、Office 365 でグローバル ルーティングを有効にするには、Azure ExpressRoute Premium Add-on が必要です。500 シート以上を持ち ExpressRoute を実装している Office 365 のお客様は、必要な  *ExpressRoute Premium Add-on*  を追加料金なしで入手できます。
  
### 優れたメディア品質を得るには ExpressRoute が必要ですか?

Azure ExpressRoute は、Skype for Business Online で最適なメディア品質を得るための要件ではありません。 ただしこれは、クラウド接続が Skype for Business ネットワーク パフォーマンス ターゲットまたはしきい値を満たすために役立つ展開オプションの 1 つです。
  
Office 365 は、インターネットを利用する高パフォーマンスでセキュリティ保護されたサービスです。 Skype では、セキュリティとパフォーマンスを継続的に改善するために、新しいセキュリティ機能および地域の Edge ノードに引き続き投資していきます。 Azure ExpressRoute は、Skype for Business Online を含む Office 365 サービスの要件ではありません。 Azure ExpressRoute は利用可能な展開オプションの 1 つで、Office 365 への接続が Skype for Business ネットワーク パフォーマンス要件を満たすことに役立ち、Skype for Business Online の最適なメディア品質エクスペリエンスを実現できるようにします。
  
Skype for Business Online メディア品質では、会社のサイトと Microsoft ネットワーク エッジ間の接続が [Skype for Business クライアントから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge)のパフォーマンス ターゲットを満たすこと、およびネットワーク エッジと Microsoft ネットワーク エッジ間の接続が[ネットワーク エッジから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_YourNetworkEdge)のパフォーマンス ターゲットを満たすことが重要です。 
  
また、内部ネットワークおよびクラウド接続機能を含む会社の物理ネットワーク接続でピーク時のメディア トラフィック量を処理できることも重要です。 Azure ExpressRoute は、Skype for Business Online クラウド接続がこれらのパフォーマンス要件すべてを満たすために役立つさまざまな方法のうちの 1 つです。
  
### ExpressRoute は音声品質 SLA に必要ですか?

いいえ。ExpressRoute は Skype for Business Online 音声品質 SLA に必要ありません。[Skype for Business Online 音声品質 SLA](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) は、適正なライセンスおよびサブスクリプション内で Skype for Business Online 音声サービス ユーザーが発信するあらゆる対象通話に適用されます。これにより、ユーザーはあらゆるタイプの VoIP または PSTN 通話を発信することができます。音声品質 SLA には、以下の状況すべてに対処することが含まれます。
  
- Microsoft 認定 IP 電話からの通話。
    
- 有線のイーサネット接続。
    
- Microsoft ネットワークの問題を原因とする音声品質の問題。
    
> [!NOTE]
> 音声品質 SLA では、ExpressRoute パートナーやその他のネットワークを含む Microsoft 以外のネットワークの問題によって通話品質の低下が引き起こされる通話は除外されます。 
  
### インターネットまたは Azure ExpressRoute?

Skype for Business Online へのネットワーク接続オプションを決定する前に、お客様は、「[Skype for Business Online に接続するためのネットワーク パフォーマンス要件](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_NetworkPerf)」に記載されているネットワーク パフォーマンス要件に基づいて、ネットワークおよび現在のインターネット接続のアセスメントを行う必要があります。
  
現在のインターネット接続を介したネットワーク パフォーマンスがピーク時にも十分なキャパシティで設定されており、サイトから Microsoft ネットワーク エッジ、およびネットワーク エッジから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件を満たす場合は、引き続き既存のインターネット接続を使用して Skype for Business Online に接続することができます。
  
会社のサイトでネットワーク パフォーマンス要件が満たされない場合は、まず既存のネットワーク サービス プロバイダーと連携して、ネットワーク パフォーマンス全体を改善することを強くお勧めします。 ただし、それでも要件が満たされない場合は、Azure ExpressRoute を使用すると Skype for Business Online クラウド接続でネットワーク パフォーマンス要件を満たす点で役立ちます。
  
Azure ExpressRoute では、以下のような追加のメリットが得られます。
  
- ネットワークと Microsoft ネットワーク間の接続の可用性のサービス レベル アグリーメント (SLA)。 ExpressRoute では、SLA で 99.9% の可用性が保証されます。
    
- Office 365 サービスに必要な帯域幅の計画と保証。 これは、ExpressRoute を使用して Office 365 トラフィックまたは Skype for Business トラフィックのみを送信して、その他すべてのインターネット トラフィックにネットワークの別のインターネット出口/入口ポイントを通過させることで実現できます。
    
- ExpressRoute は、お使いのネットワークと Microsoft ネットワークとの間で DSCP QoS マーキングを保持するよう設計されています。
    
ExpressRoute QoS の詳細とキャパシティ計画については、「[Skype for Business Online の ExpressRoute および QoS](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US)」を参照してください。
  
### Skype for Business Online 専用に Azure ExpressRoute を設定できますか?

はい。Azure ExpressRoute を設定して、会社のネットワークから Skype for Business Online 専用の優れたネットワーク接続を確保することができます。 これにより、ユーザーには最適なリアルタイム メディア品質が提供されますが、別の Office 365 サービスには引き続きインターネットを介して接続することができます。
  
ボーダー ゲートウェイ プロトコル (BGP) は、インターネットを介してネットワーク トラフィックをルーティングするために使用されるインターネット上のルーティング プロトコルです。 このプロトコルはインターネット上の自律システム (AS) 間でルーティング情報をやり取りするように設計されています。 BGP コミュニティ値は、着信ルートまたは発信ルートに適用できる属性タグです。 BGP コミュニティは主に、地理、サービスの種類、その他の条件に基づいて、指定した宛先に到達するためにどの発信リンクを使用するべきかの信号を受信 AS に対して送るために使用されます。
  
BGP 通信サポートでは、Microsoft がプレフィックスをマークして、属するサービスに基づいて適切な BGP 通信値を使用してルーティングします。Microsoft は、プレフィックスがホストされている地域を示す適切な BGP 通信値を使用して、パブリック ピアおよび Microsoft ピアでアドバタイズされたプレフィックスをマークします。通信値を信頼して適切なルーティングの決定を行い、最適なルーティングを提供することができます。Skype for Business Online BGP 通信値を使用して ExpressRoute 接続を Skype for Business Online 専用に設定することができます。詳細については、「[ExpressRoute のルーティングの要件](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/)」を参照してください。
  
## Skype for Business Online の ExpressRoute 接続シナリオ
<a name="bk_NetworkPerf"> </a>

前述の推奨事項に基づいて ExpressRoute を使用することにした場合、ここでは、入手すべき ExpressRoute 接続の場所と数についての推奨事項を説明します。
  
### オンラインのみの展開 - 単一サイト

すべてのユーザーが Skype for Business Online サービスを利用し、オフィスが物理的に一か所に集中しており、Azure ExpressRoute を展開することを決定した場合は、会社のサイトからその最寄の [ExpressRoute ピアの場所](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)までの、単一の ExpressRoute 接続を設定する必要があります。
  
以下の図は、このタイプの展開の例を示しています。 この例の Contoso は、フロリダ州オーランドにある大学です。 Contoso には、10,000 人の教員と学生がいます。 その場所から Microsoft Edge サイトへのインターネット テストでは、授業時間のピーク時に 5% を超えるパケット損失が確認されました。 十分な帯域幅をプロビジョニングして ExpressRoute を使用した Office 365 への専用接続を確保することにしました。これにより、Office 365、特に Skype for Business Online リアルタイム トラフィックのネットワークの混雑を回避することができます。 Microsoft クラウドには、ジョージア州アトランタの MeetMe サイトにある ExpressRoute を介して接続します。
  
![ExpressRoute Single Site.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### オンライのみの展開 - 同じ大陸にある複数サイト

会社で Skype for Business Online サービスを同じ地域または大陸にある複数のオフィスから使用しており、Azure ExpressRoute を実装することにした場合は、メイン サイトを ExpressRoute 経由で接続し、それからオプションで、推奨されるネットワーク パフォーマンス ターゲットを満たさない別の場所用に追加の ExpressRoute ピアを追加することをお勧めします。
  
以下の例の Contoso は、米国の旅行サービス会社です。本社はニューヨークですが、その他のオフィスは米国全土にあります。 各オフィスは、MPLS を使用して Office 365 に接続する WAN を介して相互に接続されています。 最初に、ニュージャージー州ホーボーケンにあるインターネット ルーターからニューヨークの MeetMe サイトまでの ExpressRoute 接続を設定します。 
  
このセットアップでは、ほとんどのサイトから Microsoft ネットワーク (ニューヨークの Edge サイト) へのネットワーク トラフィックは、「[Skype for Business クライアントから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge)」に説明されている Skype for Business クライアント接続のネットワーク パフォーマンス ターゲットを満たすことができます。ただし、西海岸にある Contoso の各オフィスとニューヨーク間の遅延は一方向で 50 ミリ秒を超えます。さらに、ホノルルは Contoso で 2 番目に大きいオフィスですが、ホノルルとニューヨーク間の遅延は一方向で 80 ミリ秒を超えます。これらのオフィスでユーザー向けにメディア品質を高く保つために、Contoso はサンノゼ サイトからシリコン バレーの ExpressRoute MeetMe サイト間に、西海岸の ExpressRoute 接続を追加することを決定しました。
  
![Express Router Multi-site on the same continent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### オンラインのみの展開 - 別の大陸にある複数サイト

すべてのユーザーが Skype for Business Online サービスを利用しており、オフィスが物理的に複数の大陸にわたって複数の場所にあり、Azure ExpressRoute を展開することにした場合は、各大陸のメイン サイトとその最寄の [ExpressRoute ピアの場所](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)の間で大陸ごとに最低 1 つの ExpressRoute 接続を設定する必要があります。コストとメリットに応じて、ネットワーク パフォーマンス ターゲットを満たさないサイトからの追加の ExpressRoute 接続を展開するかどうかを選択できます。
  
以下の例の Contoso は、大規模な企業法律事務所で、北米とヨーロッパの主要都市にオフィスがあります。 インターネット接続と内部ネットワークのパフォーマンスのアセスメントに基づき、Contoso は北米に 2 つの ExpressRoute 接続、ヨーロッパにあるすべてのオフィスに単一の ExpressRoute 回路を展開することにしました。
  
![ExpressRoute with multiple sites and continents.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### ハイブリッド展開

オンプレミスの Lync または Skype for Business 展開があり、ハイブリッドの Skype for Business Online 統合を実装することにした場合、Azure ExpressRoute を展開することにしたのであれば、オンプレミスの Lync または Skype for Business Edge サイトごとに少なくとも 1 つの ExpressRoute 接続、およびオフィスがある大陸ごとに少なくとも 1 つの ExpressRoute 接続を用意することをお勧めします。 コストとメリットに応じて、大陸ごとに、ネットワーク パフォーマンス ターゲットを満たさないオフィスからの追加の ExpressRoute 接続を展開するかどうかを選択できます。
  
オンプレミスの Skype for Business 展開がある場合は、『[Edge Server Planning and Deployment Guide](https://technet.microsoft.com/en-us/library/mt346417.aspx)』に従う必要があります。特に、エッジ サーバーはネットワーク外部から到達できる必要があります。通常これは、ルーティング可能なパブリック IP アドレスをエッジ サーバーに割り当てるか、ネットワーク アドレス変換 (NAT) を使用して実現します。
  
以下の例で Contoso は、オンプレミスの Skype for Business エンタープライズ VoIP をすでに展開しています。 オンプレミス ユーザーを Office 365 オンライン サービスに移行しようと考えています。 また、すべてのオンプレミスおよびオンラインのユーザーが既存の PSTN インフラストラクチャを引き続き使用できるようにするため、ハイブリッド展開を使用することにしました。 Contoso のオンプレミス データ センターおよび Skype for Business エッジ サーバーはシカゴにあります。 それらの展開について、Contoso は、シカゴのデータ センターとシカゴの ExpressRoute 間に 1 つの ExpressRoute 接続を設定することにしました。 また、ホノルル オフィスの便宜を考えて、西海岸にも ExpressRoute 接続を追加しました。
  
![ExpressRoute Hybrid.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### Cloud Connector Edition を使用したオンライン展開

Skype for Business Online Cloud Connector Edition は、オンプレミスの PSTN 接続を実装する一連のパッケージ化された仮想マシンで構成されるハイブリッド製品です。 仮想化環境に最低限の Skype for Business Server トポロジを展開することで、既存のオンプレミスの既存 PSTN 音声インフラストラクチャを介して、固定電話や携帯電話を使用して通話を発信したり受信したりすることができます。
  
Azure ExpressRoute と Cloud Connector Edition を展開することにした場合は、大陸ごとに各大陸のメイン サイトとその最寄の [ExpressRoute ピアの場所](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)の間に少なくとも 1 つの Express Route 接続を設定することをお勧めします。コストとメリットに応じて、大陸ごとに、ネットワーク パフォーマンス ターゲットを満たさないサイトからの追加の ExpressRoute 接続を展開するかどうかを選択できます。
  
オンプレミスの Skype for Business 展開がある場合は、『[Planning Guide for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/EN-US/library/mt605227.aspx)』に従う必要があります。特に、アクセス エッジ サービスと A/V エッジ サービスにはパブリック IP アドレスを割り当て、Office 365 データ センターから到達できるようにする必要があります。
  
以下の例の Contoso は、ヨーロッパの会計事務所で、ヨーロッパでいくつかの主要な国や都市にあります。コラボレーションのニーズすべてについて Skype for Business Online を契約したとき、PSTN インフラストラクチャおよび既存のキャリア契約を引き続き使用するために、物理的なオフィスを持つ各国に Cloud Connector を配置することにしました。それらすべてのサイトからMicrosoft ネットワーク エッジへのテストに基づき、ロンドンに単一の ExpressRoute 接続を配置して、「[Skype for Business クライアントから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge)」に説明されている Skype for Business クライアント接続のネットワーク パフォーマンス ターゲットを満たすことにしました。
  
![ExpressRoute Cloud Connector One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
以下は、Contoso の別の展開オプションです。 このケースでは、Cloud Connector を展開した各サイトに ExpressRoute 接続を設定することにしました。
  
![ExpressRoute Cloud Connector Two.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## 関連項目
<a name="bk_NetworkPerf"> </a>

#### 

[Skype for Business Online の ExpressRoute および QoS](20c654da-30ee-4e4f-a764-8b7d8844431d.md)

