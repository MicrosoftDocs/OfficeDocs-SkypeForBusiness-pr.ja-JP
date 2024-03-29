---
title: "Skype for Business Online の ExpressRoute および QoS"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 20c654da-30ee-4e4f-a764-8b7d8844431d
description: "Learn about using Azure ExpressRoute to have a network with bandwidth requirements and Quality of Service capability for a business class user experience. "
---

# Skype for Business Online の ExpressRoute および QoS

Office 365 と Skype for Business Online 用の Azure ExpressRoute を使用して、専用のネットワーク接続で Office 365 に接続すると、 Skype for Business アプリ専用の接続で、信頼性の高い予測可能なパフォーマンスが実現されます。また、パブリック インターネットから分離されプライバシーも確保されます。 ユーザーは、Office 365 と Skype for Business Online へのより優れたネットワーク接続を購入できるようになりました。予測可能性とビジネス クラスの信頼性が追加され、稼働時間の SLA も付いています。
  
> [!NOTE]
> [Skype for Business で使用可能な帯域幅計算ツールである Bandwidth Calculator](http://go.microsoft.com/fwlink/?LinkId=715766) には新しいバージョンが存在しますが、このドキュメントの手順では Lync 2010 および 2013 Bandwidth Calculator を使用しています。
  
## Skype for Business Online と ExpressRoute

Microsoft の ExpressRoute パートナーと連携すると、クラウド上の Skype for Business Online などのさまざまな Office 365 アプリケーションを専用接続で接続できます。 ただし、Skype for Business のリアルタイム音声/ビデオ通信機能には、これらの Office 365 のリアルタイム ワークロードをサポートするように特別に構成されたネットワーク サービスが必要です。 このサービスには、ユーザーのビジネス クラスのエクスペリエンスを実現するために、必要な量のトラフィックを伝送し、サービスの品質 (QoS) をサポートできる十分な帯域幅を持つネットワークが含まれます。
  
このドキュメントでは、管理者とネットワーク設計者向けに、リアルタイム通信をサポートするためのに必要とされる特別な要件を説明し、これらの要件をサポートできるネットワークの設計を支援するために Microsoft が提供しているツール、そしてケース スタディを用いて設計プロセスについても説明します。
  
このドキュメントの最初の部分では、[Lync 2010/2013 用 Bandwidth Calculator](http://go.microsoft.com/fwlink/?LinkId=690282) を使用したネットワーク設計について、ケース スタディで順を追って説明します。大規模なマルチサイトの Skype for Business ExpressRoute 展開のネットワーク要件を見積もります。 このドキュメントの後半では、サービスの品質 (QoS) の基本的な概念、Skype for Business のリアルタイム通信をサポートするための特別な技術の詳細、必要となるネットワーク サービスの種類について説明します。
  
ここに記載されたすべての情報により、QoS と ExpressRoute の技術の詳細や直面する具体的な課題を理解し、ツールとテクニックの実践的な知識を習得して、Skype for Business ネットワークでの ExpressRoute の展開を成功させることができます。
  
## はじめに

Skype for Business 用に ExpressRoute を準備する場合、さまざまな ExpressRoute の接続モデルやパートナーと場所の各オプションを調べ、ExpressRoute を購入して社内でプロビジョニングする方法に関するドキュメントを読んでおくことを推奨します。 準備のための参照資料をいくつか紹介します。
  
- [Azure ExpressRoute]( http://go.microsoft.com/fwlink/?LinkId=690283)
    
- [ExpressRoute の価格](http://go.microsoft.com/fwlink/?LinkId=690284)
    
- [ExpressRoute のドキュメント](http://go.microsoft.com/fwlink/?LinkId=690285)
    
## パート 1: ケース スタディ - Dewey Law, LLC. での ExpressRoute

この Dewey Law, LLC. でのケース スタディでは、 Skype for Business Online 用に ExpressRouter をサポートするためのネットワークのセットアップ、ネットワーク アクセス サービスの注文、帯域幅の要件の決定の方法を説明します。
  
 **背景** Dewy Law LLC. は、 事業所 78 か所、所属弁護士 790 名、従業員数 5,580 名の全国規模の大手法律事務所です。 本社はニューヨークにあり、支社はシカゴ、サンフランシスコ、ダラスの 3 か所、さらに全国に 24 か所の大規模な事業所と 50 か所の小規模な事業所があります。 この法律事務所が扱っている案件は大規模かつ複雑で、ほとんどの場合、ワークロードが 2 つ以上のオフィスに分散しています。 このようなネットワーク設計を使用しているため、オフィス間のネットワーク トラフィックが相当な量になっています。
  
Dewy Law LLC. は比較的新しい企業で、所属弁護士やスタッフの毎日の業務は、IT に大きく依存しています。
  
 **場所および職種別のユーザーの分布**
  
||**本社 (ニューヨーク)**|**支社 (3)**|**大規模 事業所 (24)**|**小規模 事業所 (50)**|
|:-----|:-----|:-----|:-----|:-----|
|エグゼクティブ  <br/> |20  <br/> |10  <br/> |1  <br/> |1  <br/> |
|パートナー  <br/> |150  <br/> |50  <br/> |10  <br/> |5  <br/> |
|アソシエイト  <br/> |300  <br/> |100  <br/> |20  <br/> |10  <br/> |
|パラリーガル  <br/> |400  <br/> |125  <br/> |30  <br/> |15  <br/> |
|エグゼクティブ管理者  <br/> |100  <br/> |35  <br/> |6  <br/> |3  <br/> |
|IT スタッフと一般事務  <br/> |100  <br/> |25  <br/> |3  <br/> |2  <br/> |
|サイト合計  <br/> |1,070  <br/> |345  <br/> |70  <br/> |36  <br/> |
|サイト クラス合計  <br/> |1,070  <br/> |1,035  <br/> |1,680  <br/> |1,800  <br/> |
   
### ネットワークのセットアップ

Dewey Law LLC. で安定した高品質なリアルタイム サービスを提供するには、次の基本的な要件を満たす必要があります。
  
- 停電中も音声サービスを提供できるように、ネットワークのディストリビューション スイッチとルーターが Power over Ethernet (PoE) IEEE 802.3af または 802.3at に対応している必要がある。
    
- 停電中も継続して動作できるように、ネットワークのスイッチとルーターで無停電電源装置 (UPS) を使用している必要もある。
    
    Dewey Law LLC. は LAN オフィスへの Wi-Fi 接続を使用しているため、[Skype for Business のソリューション](http://go.microsoft.com/fwlink/?LinkId=690281)の Skype for Business Wi-Fi インフラストラクチャの認定パートナーの利用が強く推奨される。
    
    > [!TIP]
    > 802.11n および 802.11ac ワイヤレス アクセス ポイントが推奨されます。 
  
- 最も重要な要件として、すべてのオフィスのすべての LAN ネットワークは、サービスの品質 (QoS) を提供できるように設定されている必要がある。 これには、PC、ノート PC、スイッチやルーターなどのすべてのネットワーク ハードウェアが含まれます。
    
以上が基本的要件ですが、Dewey Law LLC. にビジネス グレードの音声サービスを提供するには、ネットワーク サービス パートナーのマルチプロトコル ラベル スイッチング (MPLS) IP サービスを使用して Azure ExpressRoute サービスに接続することが推奨されます。 MPLS が提供する IP サービスでは、遅延、ジッター、パケット損失に関するパフォーマンスが保証されます。 ただし、MPLS を使用できない場合は、ExpressRoute データ交換パートナーに接続されているイーサネットを使用することもできます。
  
MPLS プロバイダーは、複数のレベルのサービス クラスを提供していますが、それらを表す用語はプロバイダーごとに異なります。 [Lync 2010/2013 用の Bandwidth Calculator](http://go.microsoft.com/fwlink/?LinkID=690282) に入力したデータと、さまざまな Office 365 のリアルタイム ワークロードのアプリケーションで利用可能な推奨オプションについて、プロバイダーと緊密に連携して、プロバイダー側の理解を確認する必要があります。
  
Skype for Business アプリケーションからのデータを、適切な MPLS サービス クラスにマッピングする方法には、次の 2 つのオプションがあります。
  
- DSCP (Differentiated Services Code Point) を使用するトラフィックのエンドポイント マーキング
    
- ネットワーク アクセス制御リスト (ACL) ベース
    
エンドポイント マーキングを実装するには、ドメイン内の Dewey Law LLC. のすべての Windows コンピューターで、適切な DSCP (Differentiated Services Code Point) で各パケットをマーキングする必要があります。さらに、すべてのオフィス サイトですべてのネットワーク スイッチおよびルーター上で QoS を実装して、QoS マーキングが維持され、削除されないようにする必要もあります。 ネットワーク パケットに対する DSCP マーキングにより、そのネットワーク パケットの優先度をサービス プロバイダーに伝えることができます。 **パート 2 の QoS のセクションには、DSCP に関するより詳細な情報が記載されています。**
  
ネットワークの ACL ベースの割り当てを行うために、DSCP の優先度のマーキングは、アップストリームのルーターで実装され、UDP 送信元ポートに基づいて行われます。 各アプリケーションに推奨されるポート範囲は、「[Lync Server でのネットワークの計画、監視、トラブルシューティング](http://go.microsoft.com/fwlink/?LinkId=690286)」のセクション 2.6.1.1 に記載されています。 Dewey Law LLC. 全体での QoS の実装および設計と調整し、さまざまな QoS ポリシー、パケット マーキングの不一致の可能性を認識しておくことが重要です。
  
各 ExpressRoute ネットワーク サービス プロバイダーは、リアルタイムの音声/ビデオに適したサービス クラス (CoS) を用意してします。 この CoS は、音声の場合は「完全優先転送」 (EF)、ビデオの場合は「相対的優先転送」 (AF) と呼ばれます。 音声の EF トラフィック用に購入する帯域幅のサイズの決定には、細心の注意が必要です。 これは、サービス クラスの設定よりも多くの音声トラフィックをユーザーが送信した場合、音声のサービス クラスでの条件が非常に厳しくなるためです。
  
> [!TIP]
> 音声のサービス クラスでサービス プロバイダーの契約を超えて送信されるすべてのトラフィックは直ちに破棄されるため、音声品質に直接影響します。 
  
Dewey Law LLC. の全体の設計を考えるとき、 ネットワーク全体で音声トラフィックをサポートするために必要なネットワーク帯域幅の量を正確に決定し、音声用の DSCP 設定 (DSCP EF 46) で各音声パケットを (音声パケット限定で) マーキングすることが非常に重要になります。
  
エンタープライズ ネットワークで QoS を実装するには、エンドポイントまたはルーターでは、適切なレイヤー 3 の優先度識別子 (DSCP) で各パケットをマーキングする必要があります。ネットワーク パス全体では、各スイッチおよびルーターで QoS オプションを有効にする必要があります。QoS が有効ではないネットワーク スイッチまたはルーターが 1 つでもあれば、そのスイッチまたはルーターを通過する音声/ビデオ パケットに対する QoS マーキングが無効になる可能性があります。これで、ダウンストリームのすべてのスイッチとルーターで QoS が無効になり、ExpressRoute を使用するメリットが低下します。
  
また、レイヤー 3 とレイヤー 2 の QoS 優先度の関連付けを各ポイントで定義する必要も生じます。 レイヤー 2 の優先度のメカニズムは、有線ネットワークの場合は IEEE 802.1p で、Wi-Fi ネットワークの場合は 802.11e/WMM で定義されます。 さらに重要なこととして、ネットワーク サービス プロバイダーの MPLS ネットワークに接続されているネットワーク ルーターでは、適切な MPLS のサービス クラスが維持されるように、すべての発信パケット上で DSCP の設定を維持する必要があります。
  
> [!TIP]
> QoS のセットアップに関する具体的な詳細情報については、「[Lync Server でのネットワークの計画、監視、およびトラブルシューティング]( http://go.microsoft.com/fwlink/?LinkId=760669)」のセクション 2.6 を参照してください。また、「[Skype for Business 2015: ネットワーク要件の計画](http://go.microsoft.com/fwlink/?LinkId=690287)」でその他のネットワーク計画の要件を参照することもできます。 
  
### ネットワーク アクセス サービスの注文

ExpressRoute をサポートするための QoS ネットワークの要件とメカニズムが決まれば、次の手順では、ExpressRoute ネットワーク アクセス サービスを注文します。 Microsoft ネットワーク サービス プロバイダー パートナーから Dewey Law LLC. 用の ExpressRoute アクセス サービスを注文する場合には、次の 2 つの情報を提示する必要があります。
  
- 各サイトを ExpressRoute および Office 365 に接続にするのに必要な帯域幅の合計量。
    
- Dewey Law LLC. で使用されている Skype for Business アプリのサポートに必要である各サービス クラスで必要な帯域幅の合計。 サービス クラスの帯域幅要件を決めるのは、音声、ビデオ、IM、プレゼンス、画面共有などのさまざまな Skype for Business アプリケーションのそれぞれから想定されるトラフィックの量です。
    
### Skype for Business アプリケーションの帯域幅要件の決定

Dewey Law LLC. に関して、必要な帯域幅の合計を確定したら、帯域幅の合計量をさまざまなサービス クラスにどのように分割すればよいかを知っておく必要が生じます。 例としては、各 Skype for Business アプリケーション用の帯域幅の量です。
  
Dewey Law LLC. の各サイトでのこれらの要件を決定するには、 [Lync 2010/2013 用の Bandwidth Calculator](http://go.microsoft.com/fwlink/?LinkID=690282) を使用します。 この計算ツールは Excel ベースのツールで、音声、ビデオ、電話会議、画面共有などのさまざまな Skype for Business アプリケーションの想定使用量を指定できます。 この計算ツールは、ネットワーク上の各サイトに関する、帯域幅と CoS の要件の見積もりを自動的に生成します。 Lync 2010/2013 用の Bandwidth Calculator をダウンロードすると、その使用法に関する詳細情報の説明が記載されているユーザー ガイドもダウンロードされます。
  
スプレッドシートの各種のセルは、操作しやすいように次のように色分けされます。
  
- **緑色** 一般的なデータの入力領域です。
    
- **黄色** 詳細なデータの入力領域です。 これらのセルを変更できますが、変更には注意が必要です。
    
- **赤色** 読み取り専用領域で、ロックされている入力値であり、変更できません。
    
- **灰色** 表示専用の領域です。 結果または一般的な入力領域からのデータです。
    
Dewey Law LLC. の設計プロセスを開始するには、 ユーザーのキャラクターをさまざまな "役割" に分類します。定義する各役割には、さまざまな Skype for Business アプリケーションの想定使用量 ("None"、"Low"、"Medium"、"High"、または 3 つの定義済み "Custom" 設定のいずれか) を指定できます。 これらの選択肢は "Persona" ワークシートにあります。 各選択肢には具体的な使用量 ("Low"、"Medium" または "High") が指定されていますが、各選択肢の既定値は変更可能です。 この計算ツールは、各サイトに存在する各役割のユーザー数を特定すると、それぞれの場所に必要な帯域幅の合計を計算できます。
  
また、使用する音声/ビデオ コーデック、FEC (Forward Error Correction) を使用するかどうか、および帯域幅の要件に影響するその他のシステム パラメーターを指定することもできます。 Lync 2010/2013 用の Bandwidth Calculator の既定の設定を使用することも、別のコーデックや他のシステム パラメーターを選ぶこともできます。 Dewey Law LLC. のサイト設計には、既定の設定を使用できます。 ただし、既定の設定から変更できるように、使用できるすべての選択肢が含まれるプルダウン メニューがあります。 各選択肢に使用される帯域幅は、"Codecs" ワークシートに記載されています。 いずれかの設定を変更すると、各サイトでの帯域幅とサービス クラス (CoS) の組み合わせにおける変更が更新されます。 この機能が用意されているため、実現可能であるさまざまな構成をテストし、変更が帯域幅要件に及ぼす影響を確認することができます。
  
Microsoft は、Dewey Law LLC. 用に、"エグゼクティブ/パートナー"、"アソシエイト/パラリーガル"、および "IT 管理者" の 3 つの役割を定義しました。 以下の表に、さまざまな Skype for Business アプリのユーザー プロファイルを各役割向けに設定した方法を示します。
  
 **役割と使用量プロファイル ("Persona" ワークシート - 列 A ～ P)**
  
|**役割**|**IM/プレゼンス**|**P2P 音声**|**P2P ビデオ**|**会議音声**|**会議ビデオ**|**デスクトップ共有**|**ダイヤルイン会議音声**|**Lync 2010 RTV_Type**|**リモート ユーザー**|**Lync 2013 ステレオ音声**|**Lync 2013 ビデオ画質**|**Lync 2013 P2P ビデオ ウィンドウのユーザー操作**|**Lync 2013 マルチビュー使用**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|エグゼクティブ/ パートナー  <br/> |High  <br/> |Medium  <br/> |Low  <br/> |Medium  <br/> |Medium  <br/> |なし  <br/> |Medium  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Best  <br/> |Typical  <br/> |Typical  <br/> |
|アソシエイト/ パラリーガル  <br/> |High  <br/> |Medium  <br/> |Low  <br/> |Medium  <br/> |High  <br/> |High  <br/> |Medium  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Medium  <br/> |Typical  <br/> |Typical  <br/> |
|IT 管理者  <br/> |High  <br/> |Medium  <br/> |なし  <br/> |Low  <br/> |なし  <br/> |なし  <br/> |Medium  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Medium  <br/> |Typical  <br/> |Typical  <br/> |
   
Lync 2010/2013 用の Bandwidth Calculator の "Sites" シートには、上記の表「 **場所および職種別のユーザーの分布** 」の情報を入力する必要があります。 各支社のユーザー数は同じであるため、支社は 1 つの「サイト」として定義され、それが 3 つ存在すると指定されています。 大規模営業所と小規模営業所も同様に、それぞれ 24 か所と 50 か所存在しています。
  
各役割の設定を指定した後、"Sites" ワークシートには、各サイトの各役割のユーザー数を入力する必要があります。 すべてのサイトの合計ユーザーは自動的に更新されます。 Office 365 の位置にユーザーは存在しないため、ユーザーはすべてワークシートの "Branches" 行に入力する必要があります。 すると、Lync 2010/2013 用の Bandwidth Calculator では、"WAN BW per QoS traffic class" テーブルの "Best Effort Class"、"Data Traffic Class" および "Real-time traffic class" 列にデータが入力されます。以下の表のデータで示します。
  
> [!TIP]
> また、完全なスプレッドシートには各アプリケーションの同時セッションの最大数も含まれますが、場所を節約するためにこれらの列は削除してあります。 
  
 **サイトごとの役割 - ("Sites" ワークシート - 列 A、D、I、および AI ～ AX)**
  
|**サイト名**|**サイト内ユーザーの合計**|**「いいね!」がついたサイトの合計**|**ユーザー プロファイル 1**|**プロファイル 1 のユーザー**|**ユーザー プロファイル 2**|**プロファイル 2 のユーザー**|**ユーザー プロファイル 3**|**プロファイル 3 のユーザー**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|本社  <br/> |1070  <br/> |1  <br/> |エグゼクティブ/パートナー  <br/> |170  <br/> |アソシエイト/パラリーガル  <br/> |700  <br/> |IT 管理者  <br/> |200  <br/> |
|支社  <br/> |345  <br/> |3  <br/> |エグゼクティブ/パートナー  <br/> |60  <br/> |アソシエイト/パラリーガル  <br/> |225  <br/> |IT 管理者  <br/> |60  <br/> |
|大規模営業所  <br/> |70  <br/> |24  <br/> |エグゼクティブ/パートナー  <br/> |11  <br/> |アソシエイト/パラリーガル  <br/> |50  <br/> |IT 管理者  <br/> |9  <br/> |
|小規模営業所  <br/> |36  <br/> |50  <br/> |エグゼクティブ/パートナー  <br/> |6  <br/> |アソシエイト/パラリーガル  <br/> |25  <br/> |IT 管理者  <br/> |1  <br/> |
   
 **サイトでアプリケーションごとに必要な帯域幅 (Kbps) ("Sites" ワークシート - 列 A および BQ ～ LF)**
  
|**サイト**|**SIP/IM 帯域幅のピーク**|**サイト間ピア音声帯域幅のピーク**|**サイト間ピア ビデオ帯域幅のピーク**|**音声会議帯域幅のピーク**|**ビデオ会議帯域幅のピーク**|**WAN 共有帯域幅のピーク**|**PSTN 通話用 WAN 帯域幅のピーク**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|本社  <br/> |1070  <br/> |525.30  <br/> |560.00  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |
|支社  <br/> |345  <br/> |185.40  <br/> |560.00  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |
|大規模営業所  <br/> |70  <br/> |92.70  <br/> |560.00  <br/> |102.00  <br/> |600.00  <br/> |384.00  <br/> |216.30  <br/> |
|小規模営業所  <br/> |36  <br/> |119.40  <br/> |560.00  <br/> |76.50  <br/> |600.00  <br/> |384.00  <br/> |123.60  <br/> |
   
おそらく、スプレッドシートで最も重要な列は、QoS クラス別の WAN 帯域幅が記載されている列です。以下の表にこの内容を示します。このデータは、各サイトでのアクセス接続を注文するためにネットワーク サービス プロバイダーに提示する必要がある情報の要約です。帯域幅の合計を計算するときに、営業所サイトの各タイプの帯域幅に同じタイプのサイト数を掛けるのを忘れないでください。ExpressRoute ネットワーク サービス プロバイダーに接続するには、「[Azure ExpressRoute]( http://go.microsoft.com/fwlink/?LinkId=690283)」を参照してください。
  
音声、つまり「完全優先転送」 (EF) サービス クラスの帯域幅を超えないようにすることが非常に重要です。 パケットのランダムなセットが破棄されるので、1 回の通話または通話のグループの品質が低下するのではなく、進行中のすべての通話が影響を受ける可能性があります。 また、音声以外のトラフィックが追加された場合に、EF の DSCP (つまり DSCP = 46)、または音声キューを使用して、音声のみがマークされるようにすることも非常に重要です。
  
> [!TIP]
> この場合も、EF のサービス クラスにより最適なパフォーマンスの保証が得られますが、定義済みの帯域幅を上回ると、余剰のパケットは直ちに破棄されます。 
  
 **QoS トラフィック クラスによるサイトごとの総計帯域幅 - ("Sites" ワークシート - 列 A および ML ～ MR) **
  
|**サイト名**|**ベスト エフォート クラス (DSCP 0)**|**データ通信クラス (DSCP custom)**|**リアルタイム通信クラス (DSCP 34, AF41)**|**優先通信クラス (DSCP 46, EF)**|
|:-----|:-----|:-----|:-----|:-----|
|本社  <br/> |0.00  <br/> |5764.80  <br/> |3200.00  <br/> |3953.10  <br/> |
|支社  <br/> |0.00  <br/> |2033.60  <br/> |1880.00  <br/> |1336.50  <br/> |
|大規模営業所  <br/> |0.00  <br/> |486.40  <br/> |1160.00  <br/> |411.00  <br/> |
|小規模営業所  <br/> |0.00  <br/> |438.40  <br/> |1160.00  <br/> |319.50  <br/> |
   
### 計画の実施

WAN を使用する帯域幅の合計と ExpressRoute を使用する帯域幅の量は、上の **アプリケーション/サイトごと** の表の帯域幅の見積もりを使用して計算できます。ExpressRoute を使用するトラフィック部分にサイト間ピア帯域幅は含まれません。
  
|**サイト**|**SIP/IM 帯域幅のピーク**|**音声会議帯域幅のピーク**|**ビデオ会議帯域幅のピーク**|**WAN 共有帯域幅のピーク**|**PSTN 通話用 WAN 帯域幅のピーク**|**サイト クラスごとの ExpressRoute 合計トラフィック (サイトの合計時間数)**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**本社** <br/> |1,070  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |11361.80  <br/> |
|**支社** <br/> |345  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |8704.20  <br/> |
|**大規模営業所** <br/> |70  <br/> |102.00  <br/> |600.00  <br/> |384.00  <br/> |216.30  <br/> |32935.20  <br/> |
|**小規模営業所** <br/> |36  <br/> |76.50  <br/> |600.00  <br/> |384.00  <br/> |123.60  <br/> |61005.00  <br/> |
   
つまり、ExpressRoute を使用する Skype for Business Online トラフィックはおよそ 114 Mbps ということになります。そのため、Dewey は ExpressRoute 用に少なくとも 200 Mbps のサブスクリプションが必要ということになります。ExpressRoute 回線は、ExpressRoute の複数のピアリングの場所で複数購入できます。ExpressRoute 回線の複数購入は、Dewey のサイトが地理的に異なるリージョンにある、または ExpressRoute 回線への接続に障害が発生した場合に備えて回復性を提供したい場合にお勧めです。ExpressRoute 回路を複数の Azure リージョンで購入する場合、ExpressRoute を使用してグローバル接続を受信するには ExpressRoute プレミアム アドオンが必要になります。
  
必要な帯域幅の合計量とサービス クラス (CoS) の帯域幅の数値が判明したため、選んだネットワーク サービス プロバイダーに発注することができます。他のアプリケーションやサービスのトラフィックの見積もりを忘れずに含めてください。ネットワーク計画ガイダンスは、他の Office 365 サービス用 (Exchange や OneDrive 用 Bandwidth Calculator など) にも提供しています。ネットワーク サービス プロバイダー用帯域幅サブスクリプションは、イントラサイト トラフィックを加算する必要があるため、高めになります。Lync 2010 および 2013 の Bandwidth Calculator が計算するのは、想定されるトラフィックの見積もりのみです。そのため、ストレス テストを実施するトラフィック量に対応できる能力がネットワークにあることを確認してください。 
  
> [!TIP]
> ネットワークの事前評価を行う場合には、ネットワークのストレス テストを強く推奨します。 
  
ストレス テストでは、インフラストラクチャを構築および構成してから、パフォーマンスの監視中にシミュレート済みトラフィックの想定量を使用してインフラストラクチャを稼働させます。 領域によってはトラフィックの見積もりが不正確である場合がありますが、少なくとも、Lync 2010/2013 用の Bandwidth Calculator で予測したトラフィック量をインフラストラクチャでサポートできることを確認できます。 最低でも数日はストレス テストを実行することを推奨しますが、長期間実行すれば、数値の精度を高めるのに役立ちます。 ただし、料金を支払ってはいるが、実際のユーザー ネットワーク トラフィックを伝送していないネットワーク サービスの費用と照らし合わせて、ストレス テストの期間の延長を比較検討する必要があります。 Microsoft は、ネットワーク事前評価ストレス ツールを含むネットワーク管理および運用ツールを提供するために、IT Pro Tools プログラムの一環として多くのベンダーを認定しています。 Skype for Business では、認定済み IT Pro Tools を利用してネットワーク評価を代行できるシステム インテグレーター (SI) も提供されています。 詳細については、「[Skype for Business Solutions: IT Pro Tools](http://go.microsoft.com/fwlink/?LinkID=690307)」で参照できます。
  
ストレス テストにより、必要になるトラフィック量をネットワークでサポートできることをある程度は再確認できますが、実際には、多くの理由により Lync 2010/2013 用の Bandwidth Calculator のデータが不正確になる可能性があります。 帯域幅が十分であり、QoS のメカニズムが適切に機能していることを確認するために、いったん展開されてからも継続的なネットワーク評価を行って、サイトのネットワークを引き続き監視することも検討する必要があります。 オンラインになる実際のユーザーが増えるに従って、ネットワーク パフォーマンスの監視を継続することが重要になります。
  
## パート 2: Skype for Business で QoS を実現するための ExpressRoute

Microsoft の ExpressRoute サービスは Azure クラウドへの専用接続を提供しますが、Office 365 リアルタイム ワークロードの通信サービスには、トラフィック量を伝送するのに帯域幅が十分であり、ビジネス グレードのユーザー エクスペリエンスを実現するためにサービスの品質 (QoS) をサポートできるネットワーク サービスが必要です。パスの一部で QoS をサポートできないと通話全体の品質が低下する可能性があるため、QoS 対応の接続はエンドツーエンド (PC、ネットワーク スイッチ、ルーターからクラウド) で構成されている必要があります。
  
Microsoft の ExpressRoute Exchange プロバイダーまたはネットワーク サービス プロバイダーのパートナーを使用して、IP ネットワークでリアルタイム トラフィックをサポートし、Office 365 リアルタイム ワークロードの適切な ExpressRoute 展開を構成およびサポートする場合の課題を説明することが、このセクションの目的です。
  
QoS は ExpressRoute ネットワーク回線上のお使いのネットワークのみから受け入れられ、Skype for Business トラフィック用の Microsoft ネットワーク内で使われます。 現在、Microsoft からの一部の送信接続は部分的に Skype for Business 用の DCSP 値を欠いています。 送信トラフィックが完全に DSCP 値でマーク付けされるまで、この記事の「 **ネットワーク アクセス制御リスト (ACL) を使用した QoS の実装** 」セクションで説明されている QoS マーキングをトラフィックに追加するためのガイドラインに従うことが推奨されます。
  
### リアルタイムの問題

ビジネス品質の音声/ビデオ サービスを実現するには、IP ネットワークに特別な要求が課されます。 リアルタイム トラフィックでは、UDP (User Datagram Protocol) を使用して伝送される RTP (Real-time Transport Protocol) を使用します。 エラーがないか各メッセージを番号で区別してテストし、失われたかエラーが発生したメッセージを検出して再送する別のメカニズムが含まれる TCP (Transmission Control Protocol) とは異なり、UDP ではこの種類の信頼性が提供されません。 メッセージは、エラーにより破損するかバッファー オーバーフローにより失われると、そのまま失われます。 RTP には UDP が採用されています。これはリアルタイム トラフィックの性質上、メッセージが失われると、再送信されても音声メッセージの流れにプラスの影響を与えるには到達が遅すぎるためです。
  
失われた音声パケットの影響の知見に基づき、設計者は、音声/ビデオ オーバー IP のパフォーマンスを改善する 2 つのアプローチを考案しました。
  
- パケットが失われた場合の音声エンコード/デコードの回復性を高める。この動作を行う方法としては、Office 365 リアルタイム トランスポートに存在する機能である FEC (Forward Error Correction) を使用して一定の割合の発生エラーを修正するか、Microsoft のコーデックの特徴である損失パケットの影響をマスクしようとする音声デコード システムを設計します。
    
- 遅延、パケットの損失とジッター、およびパケット間の遅延の変動に関するネットワークのパフォーマンスを保証するために、QoS のメカニズムを使用するトランスポート サービスを使用する。
    
回復力のある音声コーディングはパケット損失の問題にのみ対処するため、リアルタイム音声/ビデオの伝送に使用されるネットワークで、遅延とジッターを最小限にするメカニズムを装備することが重要です。 回復力のあるコーディングを使用しても、損失パケットが多すぎると、受信側ステーションでは、認識できる形態の音声信号を再構築するのに十分な情報が得られません。 人間に認識されるまでの音声品質の低下に至る損失パケットのパーセンテージは、使用する音声エンコードの手法に応じて異なります。 しかしいずれの場合も、一連の連続するパケットが失われると大きな問題になります。
  
遅延を最小限にするのが重要であるのは、遅延が過度であると、会話の流れに影響し、話者にとってストレスになる可能性があるためです。 ベスト プラクティスでは、音声のエンドツーエンドの遅延 (Microsoft では「口から耳まで」の遅延と呼んでいます) を、「往復」ではなく片道で 150 ミリ秒以下に抑える必要があるとされます。 もちろん、大洋を横断するリンクなどの長距離の伝送リンクでは、信号がケーブルを伝って物理的に移動するのにかかる伝搬の遅延や時間があるため、遅延は大きくなります。
  
遅延が片道で 150 ミリ秒よりも大きくなると、話者に不自然さを感じさせます。心理学的には、話者は一瞬の間を感じ、受信者には自分の声が聞こえていないと考え、最後に言ったことを繰り返します。この声が、遠端から着信する遅延した応答と衝突します。衛星チャネル経由で会話した経験があれば、この効果をご存じでしょう。 衛星チャネル経由では片道の遅延はおおよそ 250 ミリ秒であり、許容できる遅延を大きく上回っています。
  
 **ビジネス グレードの音声に推奨されるネットワーク パラメーター**
  
|**パラメーター**|**推奨値**|
|:-----|:-----|
|到着パケット間のジッター (平均)  <br/> |≤ 5ms  <br/> |
|到着パケット間のジッター (最大)  <br/> |≤ 40ms  <br/> |
|パケット損失率 (平均)  <br/> |0% に近づける  <br/> |
|ネットワーク遅延 (片道)  <br/> |≤ 100ms (遅延と地理上の距離の対比へのチェックを含める必要がある)  <br/> |
   
### ビジネス グレードのボイス ネットワークの一部としての ExpressRoute

ExpressRoute は、ネットワーク サービス プロバイダー (NSP) または Exchange プロバイダー (EXP) を介して、次の 3 つの方法のいずれかで専用接続を提供します。 
  
- Cloud Exchange コロケーション
    
- Point-to-Point Ethernet 接続
    
- Any-to-Any (IPVPN) 接続
    
これには、高可用 (稼働率 99.9% の SLA)、インターネット トラフィックの変動の影響を受けないセキュア (インターネットを利用しない) で信頼性の高いルーティングといった利点があります。また、QoS (サービスの品質) のマーキングに従ってトラフィックの優先順位付けを行います (QoS については以下で説明します)。ExpressRoute を導入し、入念に計画した WAN 環境があれば、ビジネス グレードのボイス ネットワークを構築できます。
  
ExpressRoute は、ExpressRoute 回線に接続されているオフィスやデータセンター (ハイブリッド トポロジの場合) からのデータ通信に使用できます。オフサイト ユーザー (たとえば、ホーム オフィスや出先にいるユーザー) のデータでは、ユーザーが VPN で接続されていて、ExpressRoute 回線のサイズ決定のための帯域幅見積もりに含まれる必要がない場合を除き、ExpressRoute 回線は利用しません。多国籍のお客様の場合、ExpressRoute 回線を各リージョンで購入し、BGP コミュニティ タグでルーティング ルールを指定して、ExpressRoute の優先回線 (通常は各サイトに最も近い回線) にトラフィックを誘導できます。残りの回線では、1 つの回線に影響を及ぼすような障害に備えて冗長性を確保します。 
  
### ExpressRoute を利用できない場合

コスト、ExpressRoute 要件を満たせない、または利用中の NSP の制限などの理由で、全サイトを ExpressRoute に接続できないことがあるかもしれません。ExpressRoute を利用できない場合は、引き続き後述の推奨事項に従ってネットワーク内での QoS のマーキングを実施し、また、十分な帯域幅を確保し、QoS に基づくトラフィックの優先順位付けをサポートできるように NSP との契約を計画することを推奨します。
  
また、複数のリージョンにオフィスがあるものの、すべてのリージョンに ExpressRoute 回線を用意していない場合は、サテライト オフィス間のトラフィックのルーティングの設定時にリージョンの BGP コミュニティ タグを使用し、不要な長時間通信を回避することができます。たとえば、Skype for Business Online を使用する部門を米国でホストし、事業所をヨーロッパに持つある企業を例に考えてみます。この企業の ExpressRoute 回線はシリコン バレーに 1 つしかありません。Skype for Business Online のトラフィックのほとんどは、データセンターにルーティングされ、ここでは、ほとんどのトラフィックに適した ExpressRoute 回線を使用してその部門がホストされています (たとえば、社内の他のユーザーとの電話会議など)。ただし、ヨーロッパのユーザーが、部門がヨーロッパにある別の企業がホストする電話会議に参加しようとする場合、その通話のメディアの接続先は、2 社目があるヨーロッパのデータセンターとなります。シリコン バレーにある ExpressRoute 回線を使ってトラフィックをルーティングした場合、インターネットを使用した場合に比べてあまり直接的なルートになりません。そのような場合は、ネットワーク内でルーター (たとえば、ヨーロッパのオフィス内で) を設定して、ルーティング ルールを策定する際にコミュニティ タグを調べて、ヨーロッパ リージョンのタグを持つトラフィックには、シリコン バレーの ExpressRoute 回線ではなくインターネットを使ってルーティングするようにしてください。
  
### サービスの品質 (QoS)/サービス クラス (CoS) の基本的な概念

IP では、サービスの品質 (QoS) は、ある種のパケットを他のパケットよりも優先処理するために使用するメカニズムを表します。 国際電気通信連合 (ITU) の定義によると、QoS は、遅延、損失、信号対ノイズの比率、クロストーク、エコー、割り込み、周波数応答、ラウドネス レベルなどを含む、接続のすべての品質の側面から構成されています。 パケット ネットワークで QoS に言及する場合は、より正確な名称であるサービス クラス (CoS) という用語を使用します。この用語では、遅延、ジッターおよびパケット損失のパフォーマンス改善に重点を置いていますが、この説明では、より一般的な QoS という用語を引き続き使用します。
  
IP ネットワークの通話では、次の 2 つの主要コンポーネントに QoS を提供します。
  
- リアルタイム トラフィック用の各リンクに対して定義済みである帯域幅量の予約。リアルタイム トラフィックにその帯域幅が必要でない場合はいつでも、帯域幅を他のトラフィックに使用できます。 一般的なガイダンスでは、リンクのキャパシティの 30% 以下を音声トラフィック用に割り当てる必要があります。
    
- ヘッダーの優先度インジケーターでパケットをマークすると、パスにあるスイッチとルーターには、割り当てる必要があるパケットの優先度が通知されます。
    
スイッチまたはルーターでパケットが受信されると、次のレグまたはホップに向けて、パケットは出力キューに移動されます。 優先度レベルが異なれば、出力キューが異なります。 スイッチまたはルーターは、低優先度のキューよりも高い頻度で高優先度のキューにサービスを提供するアルゴリズムを使用します。
  
課題としては、レイヤー 2 (イーサネットまたは Wi-Fi レイヤー) とレイヤー 3 (IP レイヤー) で実装される、異なる QoS のテクニックが存在しています。これらの異なる QoS の実装を、ネットワークとネットワーク サービス プロバイダーのネットワークの間にあるインターフェイスだけでなく、ネットワークの各スイッチとルーターでも構成する必要が生じる場合があります。
  
さまざまな Skype for Business アプリケーションからのデータを、適切なサービス クラスにマッピングする方法に関しては、次の 2 つのオプションがあります。
  
- DSCP (Differentiated Services Code Point) を使用するトラフィックのエンドポイント マーキング
    
- ネットワーク アクセス制御リスト (ACL) ベース
    
### エンドポイント トラフィック マーキング - DSCP (Differentiated Services Codel Point)

差別化サービス (DiffServ) は、ネットワーク トラフィックを分類および管理し、IP ネットワークで QoS を提供するための「おおまかな」メカニズムであると言われます。 レイヤー 3 の機能を実装するルーターなどのデバイスは、DSCP (DiffServ Code Point) を使用して、パケットの優先度を定義します。 IP ヘッダーの "Differentiated Services" フィールド (旧称 "Type of Service" フィールド) に 6 ビットの DSCP 値を挿入すると、QoS が実装されます。この 6 ビットにより、64 個の異なる優先度レベルを使用できます。 通常、優先度レベルは、以下に示すように定義されます。
  
 **DSCP の推奨設定**
  
|**トラフィック クラス**|**処理 (DSCP マーキング)**|**Skype for Business のワークロード**|
|:-----|:-----|:-----|
|**音声** <br/> |EF (46)  <br/> |Skype for Business および Lync の音声  <br/> |
|**対話型** <br/> |AF41 (34)  <br/> |ビデオ  <br/> |
||AF21 (18)  <br/> |アプリケーション共有  <br/> |
|**既定** <br/> |AF11 (10)  <br/> |ファイル転送  <br/> |
||CS0 (0)  <br/> |その他  <br/> |
   
 ** IP v4 ヘッダー**
  
![IPv4 のヘッダー](../images/c8a6a714-2784-4328-8297-2e62706f302d.png)
  
### レイヤー 2 QoS: IEEE 802.1p/Wi-Fi Multi-Media (IEEE 802.11e)

DSCP は、レイヤー 3 で QoS を実装するための標準的なメカニズムですが、有線 (イーサネット) とワイヤレス (Wi-Fi ネットワーク) にはさまざまなレイヤー 2 の QoS メカニズムがあります。 有線ネットワーク用の QoS メカニズムは IEEE 802.1p 規格で定義されています。WLAN QoS メカニズムは IEEE 802.11e で定義されていて、Wi-Fi Alliance で "Wi-Fi Multi-Media Certified" (WMM 認定) とされているものです。
  
IEEE 802.1p では 3 ビットの優先度コード ポイント (PCP) を使用してメッセージの優先度を識別します。PCP はイーサネット ヘッダーにある 32 ビット フィールドの一部で、VLAN の ID も伝送します。 以下に示すように、PCP 値の定義が含まれています。
  
 ** IEEE 802.1p PCP の値**
  
|**PCP の値**|**優先度**|**略語**|**トラフィックの種類**|
|:-----|:-----|:-----|:-----|
|7  <br/> |7  <br/> |NC  <br/> |ネットワーク制御  <br/> |
|6  <br/> |6  <br/> |IC  <br/> |インターネットワーク制御  <br/> |
|5  <br/> |5  <br/> |VO  <br/> |音声  <br/> |
|4  <br/> |4  <br/> |VI  <br/> |ビデオ  <br/> |
|3  <br/> |3  <br/> |CA  <br/> |クリティカル アプリケーション  <br/> |
|2  <br/> |2  <br/> |EE  <br/> |エクセレント エフォート  <br/> |
|0  <br/> |1  <br/> |BE  <br/> |ベスト エフォート  <br/> |
|1  <br/> |0  <br/> |BK  <br/> |バックグラウンド  <br/> |
   
IEEE 802.1p は、優先度レベルごとに異なる優先度のキューにトラフィックが並べ替えられる DSCP とほぼ同じ方法で実装されますが、WLAN 通話の共有メディアの性質により、別のアプローチが必要になります。 アクセス ポイントとクライアントは、異なる優先度レベルに独立した出力キューを維持しますが、無線チャネルでフレームが送出される方法にも違いがあります。
  
Wi-Fi ネットワークでは、アクセス ポイントと関連付けられているすべてのクライアントは 1 つの半二重チャネルを共有します (つまり、ある時点でフレームを送信できるのは 1 つのクライアント ステーションまたはアクセス ポイントに限られます)。 無線チャネルで競合が生じる可能性を最小限にするために、ステーションはフレームの送信前に、"フレーム間スペーシング" と呼ばれる定義済みの期間、チャネルがアイドル状態になるのを待ちます。ステーションがフレームを送信しようとしたときにチャネルがビジー状態であれば、ランダムな期間でステーションはオフ状態に戻ります。 フレームが送信されても、送信側が受信側からの受信確認メッセージを受信しないと、送信側は競合などの障害が発生したと見なし、無線チャネルにアクセスして再送信する前に、ランダムな間隔で前の段階に戻ります。 同じ 2 つのステーションが再度競合する可能性を低くするために、バックオフの間隔はランダムになっています。
  
無線チャネルへのアクセスに優先順位を付けるために、IEEE 802.11e/WMM では、AFIS (Arbitrated Inter-Frame Spacings) と呼ばれるさまざまな伝送前の待機間隔と、各種のトラフィック クラス用のさまざまなバックオフの範囲を定義しています。"アクセス カテゴリ" と呼ばれる 4 つの優先度レベルが定義されています。
  
優先度の指定には、高優先度のフレームに短期の AFIS 値を割り当てます。 そのため、あるステーションが音声フレームを送信するために待機していて、別のステーションがデータ フレームを送信するために待機している場合は、常に音声フレームが先に送信されます。 技術上は、音声フレームとビデオ フレームには同じ AFIS 値が割り当てられていますが、ビデオ フレームのバックオフ間隔の範囲の方が大きくなっています。 よって、最初の試行で音声フレームとビデオ フレームが競合した場合は、常に音声フレームの方が先に再送されます。 IEEE 802.1p と IEEE 802.11e の間の相関関係を以下に示します。
  
 ** IEEE 802.11e/Wi-Fi Multi-Media (WMM) から 802.1P へのマッピング**
  
|**WMM のアクセス カテゴリ**|**WMM 説明**|**802.1p PCP 値**|**802.1p の送信先**|
|:-----|:-----|:-----|:-----|
|1 (AC_VO)  <br/> |音声  <br/> |7 (111)  <br/> |NC  <br/> |
|6 (110)  <br/> |VO  <br/> |
|2 (AC_VI)  <br/> |ビデオ  <br/> |5 (101)  <br/> |VI  <br/> |
|4 (100)  <br/> |CL  <br/> |
|3 (AC_BE)  <br/> |ベスト エフォート データ  <br/> |3 (011)  <br/> |EE  <br/> |
|0 (000)  <br/> |BE  <br/> |
|4 (AC_BK)  <br/> |バックグラウンド データ  <br/> |1 (001)  <br/> |BK  <br/> |
|2 (010)  <br/> |---  <br/> |
   
レイヤー 3 からレイヤー 2 への優先度の関連付け (推奨値) を以下に示します。
  
 **レイヤー 3 からレイヤー 2 への優先度の関連付け (推奨値)**
  
||**レイヤー 3 のマーキング**|**レイヤー 2 (PCP 値)**|**Wi-Fi (アクセス カテゴリ)**|
|:-----|:-----|:-----|:-----|
|ネットワーク制御  <br/> |ホップ動作単位 (PHB) - クラス セレクター (CS) 6  <br/> |6  <br/> |1 (AC_VO)  <br/> |
|DSCP 値 - 48  <br/> |
|音声  <br/> |ホップ動作単位 (PHB) - 完全優先転送 (EF)  <br/> |5  <br/> |1 (AC_VO)  <br/> |
|DSCP 値 - 46  <br/> |
|ビデオ会議  <br/> |ホップ動作単位 (PHB) - 相対的優先転送 (AF) 41  <br/> |4  <br/> |2 (AC_VI)  <br/> |
|DSCP 値 - 34  <br/> |
|通話シグナリング  <br/> |ホップ動作単位 (PHB) - クラス セレクター (CS) 3  <br/> |3  <br/> |2 (AC_VI)  <br/> |
|DSCP 値 - 24  <br/> |
|低遅延データ  <br/> |ホップ動作単位 (PHB) - 相対的優先転送 (AF) 21  <br/> |2  <br/> |3 (AC_BE)  <br/> |
|DSCP 値 - 18  <br/> |
|高スループット データ  <br/> |ホップ動作単位 (PHB) - 相対的優先転送 (AF) 11  <br/> |1  <br/> |3 (AC_BE)  <br/> |
|DSCP 値 - 10  <br/> |
|ベスト エフォート  <br/> |ホップ動作単位 (PHB) - 0  <br/> |0  <br/> |4 (AC_BK)  <br/> |
|DSCP 値 - 0  <br/> |
   
IEEE 802.1p と WMM には優先符号化で不一致が存在することに注意してください。 802.1p の音声の PCP 値は 5 ですが、WMM に対する標準的な等価マッピングでは、PCP 5 はビデオ (AC_VI) に関する WMM のアクセス カテゴリであるアクセス カテゴリ 2 に変換されます。 可能であれば、PCP 5 がアクセス カテゴリ 1 に変換されるようにマッピングを上書きする必要があります。あるいは、Wi-Fi Alliance によりこの問題が解決されるまで、同一の Wi-Fi ネットワークで音声とビデオの使用を避けます。 Wi-Fi の詳細については、「[Wi-Fi カタログのアイテム]( http://go.microsoft.com/fwlink/?LinkId=690322)」を参照してください。
  
### ネットワーク アクセス制御リスト (ACL) を使用した QoS の実装

ExpressRoute 構成で QoS を実装する別の方法としては、ネットワーク アクセス制御リスト (ACL) を使用します。 そのアプローチでは、エンドポイントで各パケットのヘッダーに適切な DSCP マーキングを挿入するのではなく、UDP 送信元ポートに基づき、上位ルーターによってマーキングを行うことができます。 この場合でも、DSCP の設定を確実に維持するために、QoS をサポートするようにすべてのスイッチとルーターを構成する必要があります。 それよりも重要な点として、サービス プロバイダーのネットワークに接続されているルーターは、各パケットのヘッダーで DSCP を維持する必要があります。これは、その DSCP 設定の本質は、パケットをどのように扱えばよいかに関する、ネットワーク サービス プロバイダーに対しての指示であるためです。
  
各 Skype for Business アプリケーションに推奨されるポート範囲は、『[Lync Server でのネットワークの計画、監視、およびトラブルシューティング](http://go.microsoft.com/fwlink/?LinkId=690286)』ガイドのセクション 2.6.1.1 に記載されています。 この点を QoS に対する組織の全般的なアプローチで調整し、さまざまな QoS ポリシーと潜在的なパケット再マーキングの不一致を監視することが重要です。
  
QoS と MPLS ネットワーク サービスが使用される主な理由は、リアルタイム音声/ビデオに良好なユーザー エクスペリエンスを確保するためですが、これらの同じ機能をデータ アプリケーションに適用することもできます。 MPLS ネットワークにより、組織では、すべてのアプリケーションを平等に扱うのではなく、ある種のデータ アプリケーションを他のアプリケーションよりも優先させることができます。 MPLS を使用すると、クレジット カード取引や画面共有などのリアルタイム アプリケーションを、メールなどの時間的制約が比較的緩いトラフィックより優先させることができます。
  
### IP ネットワーク サービスの種類 - 基本的な IP と MPLS について

IP パケット転送の原型は、「ベスト エフォート」の原理で機能していました。これは、このような IP パケットを転送するルーターはパケットを宛先まで配送するために最善を尽くすが、パケットが宛先に到着する時点やその可否に関して絶対的な保証が存在しないことを意味します。 家庭用インターネット接続を含む基本的なインターネット サービスは、今日もこのように機能しています。 当初のアイデアでは、特定のアプリケーションに信頼性が必要であれば、プロトコル スタックにおいて高いレベルでアプリケーションが提供されていました。 この信頼性を備えた配信メカニズムが TCP (Transmission Control Protocol) です。 リアルタイム音声/ビデオに使用される UDP (User Datagram Protocol) は、信頼性を保証しない (つまり「ベスト エフォート」型の) 配信メカニズムです。
  
MPLS (Multi-Protocol Label Switching) は、ネットワーク サービス プロバイダーが遅延、ジッター、およびパケット損失に関するパフォーマンスを保証して IP サービスを提供するための手段として開発されました。 このようなパフォーマンスの保証に基づく配信を行うために、MPLS では、従来型の IP から予測不可能な性質を一部取り出して利用しています。 まず、ルーター間を経て宛先に至る道筋を各パケットで検出させる (結果として、送信元から宛先までパケットごとに異なる経路を辿る可能性がある) のではなく、MPLS では、LSP (Label Switched Path) と呼ばれる固定経路を使用する「仮想回線」上ですべてのパケットをルーティングします。 そのパスでいずれかのリンクに障害が発生すると、そのリンクを使用するすべての LSP で迅速に再ルーティングが行われます。
  
MPLS ネットワークにパケットが送信されると、ネットワーク サービス プロバイダーのエッジ ルーターでは、適切な LSP でのパケット転送に使用されるラベルが含まれる追加のヘッダーをパケットに付加します。 MPLS ネットワークの他端では、エッジ ルーターによってラベルが除去されます。
  
転送プロセスの単純化以外に MPLS で実現されるメリットとしては、ネットワークのすべてのリンクで転送にどの接続が使われているかが、ネットワーク管理システムで把握されます。ネットワークでトラフィックがルーティングされる方法を制御すると、運用側は、各パスで提供される QoS を保証できます。そのため、以前からの基本的な IP のベスト エフォート型のパフォーマンスとは異なり、MPLS を運用すると、パフォーマンスを予測して IP サービスを提供できます。また LSP により、MPLS はその本質上、従来のインターネット サービスよりもセキュリティが強化されています。よって、基本的な IP サービスを使用すれば、ネットワークは高品質の音声を提供するのに十分なパフォーマンスを発揮すると期待でき、また FEC などの手法やより回復力の高い音声コーディングを使用すると可能性を高めることができますが、MPLS を使用すれば、そのことを保証できます。
  
MPLS プロバイダーが提供するサービス クラスの構成要素は複数ありますが、残念ながら、プロバイダーごとに異なる用語を使用して表現しています。 [Lync 2010/2013 用の Bandwidth Calculator](http://go.microsoft.com/fwlink/?LinkID=690282) からの出力と、さまざまな Office 365 リアルタイム ワークロードのアプリケーションに推奨されるオプションをプロバイダーが確実に理解するには、プロバイダーと緊密に連携する必要があります。
  
## 結論

Skype for Business は、ビジネスの通信を実施する手段を強化します。 PBX に接続された電話、スタンドアロンのビデオ会議システム、メール用の独立したプラットフォーム、音声会議用の外部サービス、および IM とプレゼンス用の通信手段を使用するのではなく、Skype for Business によって、これらの機能のすべてを単一のユーザー インターフェイスで実現できます。
  
ビジネス グレードのリアルタイム音声/ビデオ サービスを一貫した方法で実現するには、QoS を提供できるエンドツーエンドのネットワーク インフラストラクチャが必要です。 それには、LAN と WAN 両方のサービスが含まれます。 Microsoft は、さまざまなサービスに必要になる能力を見積もる、[Lync 2010/2013 用の Bandwidth Calculator](http://go.microsoft.com/fwlink/?LinkID=690282) などのツールを提供しています。 また、IT Pro Tools プログラム ([Skype for Business Solutions: IT Pro Tools](http://go.microsoft.com/fwlink/?LinkID=690307)) には、ネットワーク インフラストラクチャの事前評価を行い、監視、レポート、およびトラブルシューティングをサポートするためのツールを提供するパートナーも存在します。 適切なサイズ計測と構成が行われたネットワーク インフラストラクチャが存在しないと、品質と一貫性に関するユーザーの期待を満たせない ExpressRoute Skype of Business 展開になってしまうリスクがあります。
  
効果的なビジネス ツールは、高い信頼性と一貫性を実現して動作し、ユーザーによる採用を促進するユーザー エクスペリエンスを提供する必要があります。 ネットワークの見地からは、LAN と WAN、固定回線とモバイル回線の両方でこの機能を実現できるネットワーク インフラストラクチャを使用することを意味します。 そのようなインフラストラクチャの計画、設計、実装および維持は、必ずしも容易ではありません。 現時点で、その機能を実現するハードウェア、ツール、およびネットワーク サービスは提供されています。ただし、それらが設計、実装および維持されている方法で、ユーザーの効率的かつ効果的な作業を可能にする一連の通信とコラボレーションのサービスを確実に利用できることと、このテクノロジが提供するサービスのメリットを組織で最大限活用できていることを確認するのは、IT 担当者の責務です。
  
## 関連項目

#### 

[ExpressRoute のドキュメント](http://go.microsoft.com/fwlink/?LinkId=690285)

