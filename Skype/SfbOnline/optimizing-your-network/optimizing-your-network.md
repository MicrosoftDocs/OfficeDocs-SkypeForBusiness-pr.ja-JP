---
title: "ネットワークを最適化します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: "次の要件は、長期的な正常性と成功をすべての skype for Business Online の機能が組織をセットアップしていることを確認する実際に重要です。一部の非常に技術的な -、このドキュメントは、ですが、いくつかのではないことがあると考えています。ヘルプを Skype for Business Online の設定が、必要な場合は、考慮すべき事項を理解するには、このドキュメントをご覧ください。Microsoft FastTrack センター、Microsoft のサービスとアカウント チーム、または Microsoft パートナーは、これらの要件を満たしているかを把握するのには、作業している場合についての注意事項も提供されます。"
ms.openlocfilehash: 1fadaa506331b7f848c007d0b97c0987c7ba212c
ms.sourcegitcommit: f0b8e01e74f63c40e4d4979efe0beef4dde1f6c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2018
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>Skype for Business Online のネットワークを最適化します。

次の要件は、長期的な正常性と成功をすべての skype for Business Online の機能が組織をセットアップしていることを確認する実際に重要です。一部の非常に技術的な -、このドキュメントは、ですが、いくつかのではないことがあると考えています。ヘルプを Skype for Business Online の設定が、必要な場合は、考慮すべき事項を理解するには、このドキュメントをご覧ください。[Microsoft FastTrack センター](https://fasttrack.microsoft.com/office)Microsoft のサービスとアカウント チームは、これらの要件を満たしているかを把握するのには、 [Microsoft パートナー](https://partnercenter.microsoft.com/en-us/pcv/search)と、作業している場合についての注意事項も提供されます。

[Skype for Business Server 2015 でユーザー モデル](../../SfBServer/plan-for-skype-for-business-server/capacity-planning/skype-for-business-server-2015-user-models.md)
  
## <a name="a-quick-overview"></a>概要

Skype for Business では、同僚や組織または世界のビジネス パートナーと接続することができます。
  
Skype for Business では、次のことができます。
  
- IM、音声、またはビデオ通話での会話を開始します。
    
- ときに、連絡先が利用できる、オンライン会議でプレゼンテーションを行うか。
    
- 会議の業務のセキュリティを設定します。
    
- 大規模な対象ユーザーをオンラインでブロードキャストします。
    
- 会議中に画面を表示または他のユーザーを制御します。
    
- [Skype for Business 他の Office プログラムを使ってチャット、通話、またはをクリックして会議に参加します。
    
## <a name="why-is-this-all-so-important"></a>理由が非常に重要ですか。

リアルタイムのメディア (オーディオ、ビデオ、およびアプリケーションの共有) オーバー IP の品質は大幅に影響を受ける-エンドツー エンド ネットワーク接続の質します。最適な Skype for Business Online のメディアの品質では、それが、会社のネットワークと Skype for Business Online の間の高品質の接続があることを確認する重要です。これを行う最適な方法では、内部ネットワークとネットワークの容量を対応するために [最大使用数トラフィック ボリュームの skype for Business Online、すべての接続に基づくクラウド接続を設定します。
  
[Microsoft パートナー](https://partnercenter.microsoft.com/en-us/pcv/search)と連携すると、さまざまな Office 365 アプリケーション Skype for Business Online クラウド リアルタイムの音声、ネットワークに接続できるし、skype for Business ビデオの通信機能が必要サービスは、次の Office 365 リアルタイム ワークロードをサポートする具体的に構成する必要があります。これには、必要なのトラフィック量を実行して、ユーザーのサービスの品質、ビジネス クラスの機能を提供するには、(QoS) をサポートしている十分な帯域幅のあるネットワークが含まれます。
  
ここで情報と共に正常を計画および for Business Online のサービスと機能とネットワークのサービスがこのような要件を満たしていることを確認するのには、Skype を展開するために役立つその他のリソースがあります。
  
- [ExpressRoute を使用して通話のフロー](call-flow-using-expressroute.md)
    
- [ExpressRoute と Skype for Business Online ネットワーク通信](expressroute-and-qos-in-skype-for-business-online.md)
    
- [メディアの品質と skype for Business Online のネットワーク接続パフォーマンス](media-quality-and-network-connectivity-performance.md)
    
## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>ビジネス用 Skype (QoS) サービスの品質を実装します。

Skype for Business Online に移動、音声、ビデオ、および共有セッションのトラフィックを処理するネットワークの容量を確認を行う必要があります。Microsoft の利用可能なその他の Office 365 サービスと、会社のサイトごとに、必要なネットワーク トラフィックを決定するための[Skype for Business の帯域幅計算機](https://www.microsoft.com/en-us/download/details.aspx?id=19011)をダウンロードします。トラフィックの量を計算して、そのトラフィックの全体的なネットワークへの影響を分析、モデリング リアルタイム コミュニケーション トラフィック メディア フローと Skype の所在地ごとのトラフィックのビジネスの金額など、使用モデリングを行う必要があります。完了したら、このデータを分析する必要がありますが向上する優れたエンド ユーザー エクスペリエンスを提供するためにキューのサイズをお勧めして、ネットワークが必要があるの推奨事項を提供します。
  
リアルタイムのトラフィックをビジネス用 Skype では、パケット損失、遅延およびジッター、混雑ネットワークで頻繁に発生する区別します。管理された外部 Wan、管理の内部 Lan および WiFi ネットワークを enterprise ベースのサービスの品質 (QoS) - - クラスのサービスとも呼ばれますを展開も必要があります。これは、適切と優先順位を Skype の音声とビデオなどのビジネス リアルタイム トラフィック用ローカル ネットワーク上の他の非リアルタイム トラフィックを wan、エンドユーザーのエクスペリエンスを向上させる作成に役立ちます。
  
(優先の転送 - DSCP 46) EF で Skype for Business の音声を展開する必要が、AF41 でキュー」と「Skype for Business ビデオを展開する必要があります (保証の転送 - DSCP 34) キューします。これは、電話システムでの Office 365 またはその他のテレフォニー機能を展開するかどうかに関係なく、ピア ツー ピアおよび会議のトラフィックにも当てはまります。
  
既存の QoS ポリシー IP テレフォニーの他の製品の LAN および WAN に既に格納する可能性があります、中には、Skype for Business は、ユーザーとサービスを使用して別の場所に移動するには、モバイルを許可します。このため、QoS ポリシーする必要がありますのマークが付いて LAN、WAN およびワイヤレス ネットワークの管理されたネットワーク経由でビジネス トラフィック用のすべての Skype を優先順位付けされていることを確認してください。
  
ネットワークのサイズを変更するために、 [Skype for Business の帯域幅計算機](https://www.microsoft.com/en-us/download/details.aspx?id=19011)をダウンロードします。
  
詳細については、メディアの品質と QoS、[メディアの品質と Skype for Business Online でネットワーク接続のパフォーマンス](media-quality-and-network-connectivity-performance.md)を参照してください。
  
詳細については、セットアップと管理 QoS、[サービスの品質を管理する](https://technet.microsoft.com/en-us/library/gg425841.aspx)を参照してください。
  
## <a name="bypass-proxies-and-wan-optimization-devices"></a>プロキシを使用しないと WAN 最適化デバイス

すべての Office 365 for Business Online Skype を含む暗号化されており、通常ことはできませんプロキシ デバイスを検査します。これらの理由により、 [Office 365 の Url と IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)に、ユーザーの接続として定義されたすべての Office 365 ネットワーク トラフィックのプロキシ デバイスを使用してをお勧めします。プロキシのデバイスがリアルタイムの Skype for Business Online のメディア ストリームで遅延が生じるので、そのトラフィックのでは、少なくともプロキシ デバイスを使用してを強くお勧めします。
  
Office 365 のトラフィックのファイアウォールに送信する PAC ファイルを使用して Office 365 の Url を除外することをお勧めします。
  
すぎる場合に役立ついくつかの利用可能なリソースを紹介します。
  
- [基準計画とパフォーマンスの履歴を使用して、office 365 パフォーマンスのチューニング](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
    
- [ネットワークと Office 365 の移行計画](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)
    
- [Office 365 プロキシ Pac ジェネレーター](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)
    
- [Office 365 を使って WAN 最適化コント ローラーまたはトラフィック/検査デバイスを使用します。](https://aka.ms/kb2690045)
    
- [Office 365 向け ExpressRoute とルーティング](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)
    
## <a name="bypass-double-encryption"></a>二重の暗号化を使用しません。

最適な考えられるオーディオとビデオのエクスペリエンスは、ユーザーを提供するには、しないように Skype for Business メディア (音声とビデオ) 仮想プライベート ネットワーク (VPN) トンネルを通過するソリューションを実装する必要があります。トランスポート層セキュリティ (TLS) を暗号化するビジネス トラフィック用のすべての Skype とメディアのワークロードをセキュリティで保護されたリアルタイム プロトコル (SRTP) を暗号化します。TLS 暗号化シグナリングされ、メディア ワークロード SRTP 暗号化されます。このトラフィック VPN トンネルでは、暗号化、およびその他のネットワーク ホップのクライアントと Office 365 の間の余分なレイヤーを追加するには、送信の可能性があります機能性が低下セッション ジッター、パケット損失と待機時間が低下するため。
  
1 つのオプションから VPN トンネルを通過するビジネス トラフィック用 Skype を防ぐためには、分割トンネルです。分割トンネルを実装するには、顧客は、VPN ベンダーのソフトウェアで次の操作方法の詳細を参照してください。
  
> [!NOTE]
> これは、Skype for Business のメディアのワークロードに必要なし、その他の Office 365 サービスに適用されていません。 
  
追加情報:
  
- [Lync のメディア VPN トンネルのバイパスを有効にします。](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)
    
- [詳細については、直接アクセス、トンネルの分割] と [強制トンネル](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)
    
- [直接アクセスを有効にします。](https://technet.microsoft.com/en-us/library/jj574163.aspx)
    
## <a name="ensure-the-right-ports-and-protocols-are-open"></a>右側のポートとプロトコルを開いていることを確認します。

ユーザーには、Url および IP の到達ことを確認する必要があります O365 サービスに必要なアドレスです。すべての Skype for Business Online の Url と IP アドレスの完全な一覧については、 [Office 365 の Url と IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)を参照してください。
  
Skype for Business のクライアントは、さまざまなポートとプロトコルを使用します。対話 (ピア ツー ピア vs マルチパーティ) の種類によって異なります方向と Skype for Business セッションのためのネットワーク トラフィックの流れとによっては、コンテンツの共有と音声/ビデオを使用します。確認して、元と移行先ポートに特別な注意を払いのポートとプロトコル] の一覧を開く必要があります。たとえば、オーディオ トラフィックだけ 20 ポート (50000 50019 TCP/UDP) を使用して、クライアント側にあるが接続先ポート任意の場所でサービスの横にある 10 K ポート範囲 (50000 59999 TCP/UDP)。これには、ファイアウォールの TCP 443、UDP 3478 を開いても含まれます。
  
その他のネットワークの構成を必要も Skype for Business Online をサポートしてがあります。
  
  
## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>使用の携帯電話とデバイス向けに Skype の最適化

リアルタイム メディア セッションでは、ヘッドセットや web カムなどのすべての参加者が使用されているメディア デバイスは、全体的なオーディオとビデオの品質にとても便利な影響を与えます。低品質デバイスまたは正しくないデバイス ドライバーのデバイスのビデオとオーディオの下の画像の品質の下の全体的な音声品質が生成されます。認定済みのデバイスまたはデバイスの品質、に関するヘルプ一方で、[キャンセル通知をエコー、ノイズ フィルター処理、ビデオの解像度がし、待機時間を削減します。
  
電話とデバイス エンドユーザーの音声とビデオの品質に大きな違いを作成します。Skype for Business の証明書プログラム「Lync 互換性のある」プログラムの進化は、デバイスが音声とビデオの Microsoft の基準を満たしていることを確認します。IP 電話、USB オーディオおよびビデオ デバイス、Pc との会議室デバイスをテストおよび Microsoft によって修飾された数値があります。組織内 Skype for Business、およびさまざまなニーズを満たすために別のデバイスを提供する作業用に最適化されたデバイスのリストとエンドユーザーの個人設定を確認する必要があります。
  
サポートされていると、認定済みのデバイスでの詳細については、次を参照してください。  
  
- [Skype for Business Online 電話を取得します。](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)
    
- [Skype for Business の電話とデバイス](https://technet.microsoft.com/en-us/office/dn947482.aspx)
    
- [個人の周辺のソリューション カタログ](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)
    
- [Microsoft Lync の認定された電話とデバイス](https://technet.microsoft.com/en-us/office/dn788944.aspx)
    
環境とユーザーの会議とオーディオおよびビデオ デバイスを使用している配列を周囲の領域は、オーディオとビデオの品質を別の大きな要因です。ノイズの環境からダイヤルインするユーザーがいるエコー、こもった感じ不明確な音声されます。濃いまたは低簡易環境でのユーザーはビデオの消去、明るい画像の品質を作成することはできません。会議室では、マイクとビデオ デバイスの場所は、参加者が受信するサウンドと画像の品質に直接影響を与えます。
  
明確に把握するユーザーの音声とビデオのエクスペリエンスの使用の Skype for Business アプリ**ツール**に > **オプション** > **オーディオ デバイス**または**ビデオ デバイス**で使用するデバイスを変更するの設定をカスタマイズします。**通話品質の確認**] をクリックして、音声通話の品質を確認することもできます。**通話品質の確認**] をクリックした場合は、品質とテスト通話が検出された問題を報告ができます。
  
![Skype for Business クライアントの音声をテストします。](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
## <a name="related-topics"></a>関連トピック 

[ExpressRoute と Skype for Business Online ネットワーク通信](expressroute-and-qos-in-skype-for-business-online.md)
  

