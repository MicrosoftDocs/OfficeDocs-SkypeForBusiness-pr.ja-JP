---
title: ネットワークの最適化
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: 組織のために設定しているすべての Skype for Business Online の機能を長期間にわたり健全で正常に使用するには、次の要件に従うことが重要です。このドキュメントは技術的な専門性に長けているユーザー向けですが、専門的な知識がないユーザーにとっても参考になります。Skype for Business Online の設定でサポートが必要な場合は、このドキュメントをお読みの上、検討する必要がある事項についてよく理解するようにしてください。このドキュメントは、Microsoft FastTrack Center、お客様の Microsoft Services とアカウント チーム、または Microsoft パートナーと連携してこれらの要件に適合できる方法を見つけ出すときに検討が必要な内容も記載しています。
ms.openlocfilehash: 6aae90775aebd7384551d8e00dfe3d0dbe0c76fb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297828"
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>Skype for Business Online 向けのネットワークの最適化

[] 組織のために設定しているすべての Skype for Business Online の機能を長期間にわたり健全で正常に使用するには、次の要件に従うことが重要です。このドキュメントは技術的な専門性に長けているユーザー向けですが、専門的な知識がないユーザーにとっても参考になります。Skype for Business Online の設定でサポートが必要な場合は、このドキュメントをお読みの上、検討する必要がある事項についてよく理解するようにしてください。このドキュメントは、[Microsoft FastTrack Center](https://fasttrack.microsoft.com/office)、お客様の Microsoft Services とアカウント チーム、または [Microsoft パートナー](https://partnercenter.microsoft.com/en-us/pcv/search)と連携してこれらの要件に適合できる方法を見つけ出すときに検討が必要な内容も記載しています。
  
## <a name="a-quick-overview"></a>簡単な概要

Skype for Business を使うと、社内または世界中の同僚やビジネス パートナーと連絡することができます。
  
Skype for Business では次のことができます。
  
- IM、音声、ビデオ通話で会話を開始する。
    
- オンライン、会議、発表で連絡先がいつ利用可能かを確認する。
    
- 業務用の強力なセキュリティを会議に設定する。
    
- オンラインでの多数の出席者に対するブロードキャスト。
    
- 会議中に自分の画面を表示したり、他の出席者による制御を許可する。
    
- Skype for Business を他の Office プログラムで使用して、ワンクリックでチャット、通話、会議に参加する。
    
## <a name="why-is-this-all-so-important"></a>これがすべて重要である理由。

IP 上のリアルタイム メディア (オーディオ、ビデオ、アプリケーション共有など) の品質は、エンド ツー エンドのネットワーク接続の品質に大きく影響されます。Skype for Business Online メディアの最適な品質を得るために、会社のネットワークと Skype for Business Online 間の接続が高品質であることを確認することが重要です。これを達成するためには、内部ネットワークとクラウド接続を、接続全体にわたって Skype for Business Online のピーク時のトラフィック量を処理するネットワークのキャパシティに基づいて設定することが最善の方法になります。
  
[Microsoft パートナー](https://partnercenter.microsoft.com/en-us/pcv/search)と連携して、クラウド内の Skype For business Online などのさまざまな Office 365 アプリケーションをネットワークに接続して、Skype for business の音声とビデオによる通信機能をリアルタイムで利用することができます。サービスは、特にこれらの Office 365 のリアルタイムのワークロードをサポートするように構成する必要があります。 これには、必要なトラフィック量を伝送するための十分な帯域幅を備えたネットワークと、ユーザーに対してビジネスクラスのエクスペリエンスを実現するためにサービスの品質 (QoS) をサポートできるものが含まれます。
  
ここで記載されている情報に加えて、次のリソースが Skype for Business Online のサービスと機能を正しく計画、展開することや、お使いのネットワーク サービスが要件と満たしているかを確認するのに役立ちます。
  
- [ExpressRoute を使用したコール フロー](call-flow-using-expressroute.md)
    
- [Skype for Business Online での ExpressRoute および QoS](expressroute-and-qos-in-skype-for-business-online.md)
    
- [Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](media-quality-and-network-connectivity-performance.md)
    
## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>Skype for Business のサービスの品質 (QoS) の実装

Skype for Business Online に移行する前に、音声、ビデオ、セッションのトラフィックの共有を処理するためのネットワークに目を向ける必要があります。他の Office 365 サービスと同様に、Microsoft は、会社の各サイトで必要なネットワーク トラフィックを判別するために使用される [Skype for Business Bandwidth Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=19011) をダウンロードで提供しています。会社のサイト別のリアルタイムの通信トラフィック メディア フローと Skype for Business トラフィックの量のモデリングを含む、使用状況のモデリングと、トラフィック量の計算と、トラフィックによるネットワーク全体への影響の分析を実行する必要があります。これを完了すると、このデータの分析によりお使いのネットワークで改善が必要な点についての推奨事項が提示され、優れたエンド ユーザー エクスペリエンスを実現するためのキュー サイズも提案されます。
  
Skype for Business のリアルタイム トラフィックは、混雑したネットワークで頻繁に発生するパケット損失、遅延、ジッターの影響を受けやすいです。サービスの品質 (QoS) は、サービス クラスと呼ばれることもありますが、管理対象の外部 WAN、管理対象の内部 LAN、およびエンタープライズ ベースの WiFi ネットワークでも展開する必要があります。これにより、ローカル ネットワーク上や WAN を経由する非リアルタイム トラフィックよりも、音声やビデオなどの Skype for Business のリアルタイム トラフィックを正しく優先させることができます。
  
Skype for Business の音声は EF (完全優先転送 - DSCP 46) キューで展開される必要があります。Skype for Business のビデオは AF41 (相対的優先転送 - DSCP 34) で展開される必要があります。これは、Office 365 の電話システムまたはその他のテレフォニー機能が展開されているかどうかに関係なく、ピアツーピアおよび会議トラフィックにも当てはまります。
  
既存の QoS ポリシーが、その他の IP テレフォニー製品での LAN または WAN 上で確立している中で、Skype for Business ではユーザーがサービスを使用中でもモバイルでの利用に切り替えたり、場所を移動したりすることが可能になります。このため、すべての Skype for Business トラフィックに対して管理対象ネットワーク全体にわたり必ず優先順位が付けられるようにするために、QoS ポリシーは LAN、WAN、およびワイヤレスネットワークでマーク付けされる必要があります。
  
ネットワークのサイズ変更を行いやすくするために、[Skype for Business Bandwidth Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=19011) をダウンロードします。
  
メディアの品質と QoS の詳細については、「 [Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](media-quality-and-network-connectivity-performance.md)」をご覧ください。
  
QoS の設定と管理の詳細については、「[サービスの品質の管理](https://technet.microsoft.com/en-us/library/gg425841.aspx)」をご覧ください。
  
## <a name="bypass-proxies-and-wan-optimization-devices"></a>プロキシと WAN 最適化デバイスをバイパスする

Skype for Business Online を含めて Office 365 はすべて暗号化され、通常はプロキシ デバイスでは検査できません。このような理由により、ユーザーが [Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)への接続として定義したように、すべての Office 365 ネットワーク トラフィックについてプロキシ デバイスをバイパスすることをお勧めします。プロキシ デバイスはリアルタイムの Skype for Business Online メディア ストリームでは遅延を引き起こす可能性があるため、それらのトラフィックではプロキシ デバイスを可能な限りバイパスすることをお勧めします。
  
Microsoft は、PAC ファイルを使用して Office 365 の URL が Office 365 トラフィックをファイアウォールに送信しないようにすることを推奨します。
  
次のいくつかのリソースに記載されている情報もご覧ください。
  
- [ベースラインとパフォーマンス履歴を使用して、Office 365 のパフォーマンスをチューニングする](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
    
- [Office 365 のネットワークと移行計画](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)
    
- [Office 365 プロキシ PAC ジェネレータ](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)
    
- [Office 365 での WAN 最適化コントローラーおよびキャッシュ デバイスの使用](https://aka.ms/kb2690045)
    
- [Office 365 向け ExpressRoute でのルーティング](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)
    
## <a name="bypass-double-encryption"></a>二重暗号化をバイパスする

可能な限りの最良の音声とビデオのエクスペリエンスをユーザーに提供するために、Skype for Business のメディア (音声とビデオ) が仮想プライベート ネットワーク (VPN) トンネルを使用しないようにするソリューションを実装する必要があります。すべての Skype for Business トラフィックはトランスポート層セキュリティ (TLS) で暗号化され、メディアのワークロードは Secure Real Time Protocol (SRTP) で暗号化されます。シグナリングは TLS で暗号化され、メディアのワークロードは SRTP で暗号化されます。このトラフィックを VPN トンネル経由で送信すると、暗号化の追加の層が追加され、追加のネットワークがクライアントと Office 365 の間をホップします。これらの両方とも、ジッター、パケット損失、遅延が増えることが原因でセッションの低下を生じる可能性があります。
  
Skype for Business トラフィックが VPN トンネルを使用しないようにするための 1 つのオプションが分割トンネリングです。分割トンネリングを実装する場合は、お客様がお使いのソフトウェアでのその方法の詳細について、ご自身の VPN ベンダーに問い合わせる必要があります。
  
> [!NOTE]
> これは、Skype for Business のメディアのワークロードについてのみ必要です。他の Office 365 サービスには適用されません。 
  
追加情報:
  
- [Enabling Lync Media to Bypass a VPN Tunnel (Lync メディアが VPN トンネルをバイパスするようにする)](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)
    
- [More on Direct Access, Split Tunneling and Force Tunneling (DirectAccess での分割トンネリングと強制トンネリングの詳細情報)](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)
    
- [Enable Direct Access (DirectAccess を有効にする)](https://technet.microsoft.com/en-us/library/jj574163.aspx)
    
## <a name="ensure-the-right-ports-and-protocols-are-open"></a>正しいポートとプロトコルが開いていることを確認する

お客様は、O365 サービスで必要となる URL と IP アドレスにアクセス可能であるか確認する必要があります。Skype for Business Online のすべての IP アドレスと URL のリストについては、「[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)」をご覧ください。
  
Skype for Business クライアントは、さまざまなポートとプロトコルを使用します。 Skype for Business セッションのネットワーク トラフィックの向きと流れは、相互作用の種類 (ピアツーピア、マルチパーティ) によって、およびコンテンツ共有と音声/ビデオの使用に応じて、異なります。 接続元と接続先のポートについて特に注意しながら、ポートとプロトコルのリストを確認して開く必要があります。 たとえば、音声トラフィックは 20 個のポート (50000 から 50019 までの TCP/UDP) をクライアント側で使用しますが、送信先のポートがサービス側で 10000 個のポートの範囲内 (50000 から 59999 までの TCP/UDP) にある可能性があります。送信先のポートには、ファイアウォール上の開いている TCP 443 と UDP 3478 も含まれます。
  
Skype for Business Online をサポートするために追加のネットワーク構成が必要になる可能性もあります。
  
  
## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>Skype for Business 用に最適化された電話機およびデバイスを使用する

リアルタイム メディア セッションでは、ヘッドセットや Web カメラなどの参加者全員が使用するメディア デバイスは、オーディオとビデオの全体的な品質に大きく影響します。 低品質デバイスまたは不適切なデバイスドライバーを使用しているデバイスでは、オーディオ品質が低くなり、ビデオの画質が低下します。 一方、認定デバイスまたは高品質なデバイスは、エコー キャンセル、ノイズ フィルタリング、ビデオ解像度、遅延低減に役立ちます。
  
電話機とデバイスによって、エンド ユーザーの音声とビデオの品質に大きな違いが生じます。Skype for Business 認定プログラムは「Lync 互換」プログラムが発展したもので、デバイスが音声とビデオに関する Microsoft 標準に適合しているかを検証します。数多くの IP 電話、USB オーディオとビデオ デバイス、PC、および会議室が Microsoft によりテストされ、認定されています。お客様は Skype for Business 用に最適化されたデバイスのリストを確認して、ご自身および組織のエンド ユーザーのさまざまなニーズと個人設定に合わせて異なるデバイスを用意するよう努める必要があります。
  
サポートされている認定済みデバイスの詳細については、次をご覧ください。  
  
- [Skype for Business Online で使う電話を入手する](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)
    
- [Skype for Business の電話とデバイス](https://technet.microsoft.com/en-us/office/dn947482.aspx)
    
- [個人用周辺機器のソリューション カタログ](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)
    
- [Microsoft Lync で認定済みの電話とデバイス](https://technet.microsoft.com/en-us/office/dn788944.aspx)
    
ユーザーが会議を行い、オーディオ デバイスとビデオ デバイスを使用する環境と周辺領域は、オーディオとビデオの品質のもう 1 つの要因です。ノイズのある環境から通話しているユーザーのオーディオは、エコーがかかり、こもっていて、不明瞭です。暗くて照明が不十分な環境にいるユーザーは、ビデオで明るくクリアな画質を実現することができません。会議室の設定で、マイクとビデオ デバイスの場所は、参加者が受信する音声と画像の品質に直接影響します。
  
ユーザーのオーディオとビデオのエクスペリエンスをより明確にするために、Skype for business アプリの**ツール** > **オプション** > の**オーディオデバイス**または**ビデオデバイス**を使って、使用中のデバイスに変更を加え、設定をカスタマイズします。 通話の音質を確認するには、[**通話品質の確認**] をクリックします。 If they click **Check Call Quality**, they can then report the quality and issues found with the test call.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
## <a name="related-topics"></a>関連トピック 

[Skype for Business Online の ExpressRoute および QoS](expressroute-and-qos-in-skype-for-business-online.md)
  
  
 
