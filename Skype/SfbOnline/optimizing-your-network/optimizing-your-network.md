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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: 組織のために設定しているすべての Skype for Business Online の機能を長期間にわたり健全で正常に使用するには、次の要件に従うことが重要です。このドキュメントは技術的な専門性に長けているユーザー向けですが、専門的な知識がないユーザーにとっても参考になります。Skype for Business Online の設定でサポートが必要な場合は、このドキュメントをお読みの上、検討する必要がある事項についてよく理解するようにしてください。このドキュメントは、Microsoft FastTrack Center、お客様の Microsoft Services とアカウント チーム、または Microsoft パートナーと連携してこれらの要件に適合できる方法を見つけ出すときに検討が必要な内容も記載しています。
ms.openlocfilehash: 1c4af624a59e0606b3ee5f9c115ad61a65dffbd0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586025"
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>Skype for Business Online 向けのネットワークの最適化

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] 組織のために設定しているすべての Skype for Business Online の機能を長期間にわたり健全で正常に使用するには、次の要件に従うことが重要です。このドキュメントは技術的な専門性に長けているユーザー向けですが、専門的な知識がないユーザーにとっても参考になります。Skype for Business Online の設定でサポートが必要な場合は、このドキュメントをお読みの上、検討する必要がある事項についてよく理解するようにしてください。このドキュメントは、[Microsoft FastTrack Center](https://fasttrack.microsoft.com/office)、お客様の Microsoft Services とアカウント チーム、または [Microsoft パートナー](https://partnercenter.microsoft.com/pcv/search)と連携してこれらの要件に適合できる方法を見つけ出すときに検討が必要な内容も記載しています。

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

[Microsoft](https://partnercenter.microsoft.com/pcv/search)パートナーと一緒に作業すると、クラウドの Skype for Business Online を含むさまざまな Microsoft 365 または Office 365 アプリケーションをネットワークに接続できます。また、Skype for Business のリアルタイム音声およびビデオ通信機能では、これらの Microsoft 365 と Office 365 のリアルタイム ワークロードをサポートするようにネットワーク サービスを特別に構成する必要があります。 これには、必要な量のトラフィックを運ぶのに十分な帯域幅を持ち、ユーザーにビジネス クラスのエクスペリエンスを提供するためにサービス品質 (QoS) をサポートできるネットワークが含まれます。

ここで記載されている情報に加えて、次のリソースが Skype for Business Online のサービスと機能を正しく計画、展開することや、お使いのネットワーク サービスが要件と満たしているかを確認するのに役立ちます。

- [ExpressRoute を使用したコール フロー](call-flow-using-expressroute.md)

- [Skype for Business Online の ExpressRoute および QoS](expressroute-and-qos-in-skype-for-business-online.md)

- [Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](media-quality-and-network-connectivity-performance.md)

## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>Skype for Business のサービスの品質 (QoS) の実装

Skype for Business Online に移行する前に、音声、ビデオ、セッションのトラフィックの共有を処理するためのネットワークに目を向ける必要があります。 他の Microsoft 365 および Office 365 サービスと同様に、Microsoft は、会社の各サイトに必要なネットワーク トラフィックを決定するために使用される[Skype for Business Bandwidth Calculator](https://www.microsoft.com/download/details.aspx?id=19011)をダウンロードできます。 会社のサイト別のリアルタイムの通信トラフィック メディア フローと Skype for Business トラフィックの量のモデリングを含む、使用状況のモデリングと、トラフィック量の計算と、トラフィックによるネットワーク全体への影響の分析を実行する必要があります。 これを完了すると、このデータの分析によりお使いのネットワークで改善が必要な点についての推奨事項が提示され、優れたエンド ユーザー エクスペリエンスを実現するためのキュー サイズも提案されます。

Skype for Business のリアルタイム トラフィックは、混雑したネットワークで頻繁に発生するパケット損失、遅延、ジッターの影響を受けやすいです。サービスの品質 (QoS) は、サービス クラスと呼ばれることもありますが、管理対象の外部 WAN、管理対象の内部 LAN、およびエンタープライズ ベースの WiFi ネットワークでも展開する必要があります。これにより、ローカル ネットワーク上や WAN を経由する非リアルタイム トラフィックよりも、音声やビデオなどの Skype for Business のリアルタイム トラフィックを正しく優先させることができます。

Skype for Business EF (Expedied Forwarding - DSCP 46) キューにオーディオをデプロイする必要があります。また、Skype for Business ビデオは AF41 (Assured Forwarding - DSCP 34) キューにデプロイする必要があります。 これは、Microsoft 365 または Office 365 の 電話システム や他のテレフォニー機能がデプロイされているかどうかに関係なく、ピアツーピアおよび会議トラフィックの場合でも当てはまる場合です。

既存の QoS ポリシーが、その他の IP テレフォニー製品での LAN または WAN 上で確立している中で、Skype for Business ではユーザーがサービスを使用中でもモバイルでの利用に切り替えたり、場所を移動したりすることが可能になります。このため、すべての Skype for Business トラフィックに対して管理対象ネットワーク全体にわたり必ず優先順位が付けられるようにするために、QoS ポリシーは LAN、WAN、およびワイヤレスネットワークでマーク付けされる必要があります。

ネットワークのサイズ変更を行いやすくするために、[Skype for Business Bandwidth Calculator](https://www.microsoft.com/download/details.aspx?id=19011) をダウンロードします。

メディアの品質と QoS の詳細については、「 [Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](media-quality-and-network-connectivity-performance.md)」をご覧ください。

QoS の設定と管理の詳細については、「[サービスの品質の管理](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md)」をご覧ください。

## <a name="bypass-proxies-and-wan-optimization-devices"></a>プロキシと WAN 最適化デバイスをバイパスする

Microsoft 365 Online をOffice 365またはSkype for Businessは暗号化され、通常はプロキシ デバイスで検査できません。 これらの理由から、ユーザーが Office 365 URL と IP アドレス範囲 に対して行う接続として定義されている、すべての Microsoft 365 および Office 365 ネットワーク トラフィックに対してプロキシ デバイスをバイパスすることをお[勧めします](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。 プロキシ デバイスはリアルタイムの Skype for Business Online メディア ストリームでは遅延を引き起こす可能性があるため、それらのトラフィックではプロキシ デバイスを可能な限りバイパスすることをお勧めします。

MICROSOFT では、PAC Microsoft 365をOffice 365してトラフィックをファイアウォールに送信Microsoft 365、Office 365 URL を除外Office 365勧めします。

次のいくつかのリソースに記載されている情報もご覧ください。

- [Microsoft 365およびパフォーマンス履歴Office 365使用してパフォーマンスチューニングを行う](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- [ネットワークと移行の計画 :Microsoft 365またはOffice 365](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)

- [Office 365 プロキシ PAC ジェネレータ](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)

- [WAN 最適化コントローラーまたはトラフィック/検査デバイスを使用して、Microsoft 365またはOffice 365](/office365/troubleshoot/miscellaneous/office-365-third-party-network-devices)

- [ExpressRoute を使用したルーティング (Microsoft 365またはOffice 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)

## <a name="bypass-double-encryption"></a>二重暗号化をバイパスする

ユーザーに可能な限り最高のオーディオとビデオのエクスペリエンスを提供するには、Skype for Business メディア (オーディオとビデオ) が仮想プライベート ネットワーク (VPN) トンネルを通過するのを防ぐソリューションを実装する必要があります。 すべてのSkype for Businessトランスポート層セキュリティ (TLS) で暗号化され、メディア ワークロードは Secure Real Time Protocol (SRTP) で暗号化されます。 シグナルは TLS で暗号化され、メディア ワークロードは SRTP で暗号化されます。 VPN トンネルを使用してこのトラフィックを送信すると、暗号化のレイヤーが追加され、クライアントと Microsoft 365 または Office 365 の間にネットワーク ホップが追加されます。この両方で、ジッター、パケット損失、待機時間が増加するためにセッションが低下する可能性があります。

Skype for Business トラフィックが VPN トンネルを使用しないようにするための 1 つのオプションが分割トンネリングです。分割トンネリングを実装する場合は、お客様がお使いのソフトウェアでのその方法の詳細について、ご自身の VPN ベンダーに問い合わせる必要があります。

> [!NOTE]
> これは、一部のメディア Skype for Businessにのみ必要であり、他のサービスやサービスにはMicrosoft 365適用Office 365できません。

追加情報:

- [Enabling Lync Media to Bypass a VPN Tunnel (Lync メディアが VPN トンネルをバイパスするようにする)](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)

- [More on Direct Access, Split Tunneling and Force Tunneling (DirectAccess での分割トンネリングと強制トンネリングの詳細情報)](/archive/blogs/tomshinder/more-on-directaccess-split-tunneling-and-force-tunneling)

- [Enable Direct Access (DirectAccess を有効にする)](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574163(v=ws.11))

## <a name="ensure-the-right-ports-and-protocols-are-open"></a>正しいポートとプロトコルが開いていることを確認する

お客様は、サービスまたはサービスに必要な URL と IP アドレスの到達可能性Microsoft 365必要Office 365があります。 Skype for Business Online のすべての IP アドレスと URL のリストについては、「[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)」をご覧ください。

Skype for Business クライアントは、さまざまなポートとプロトコルを使用します。 Skype for Business セッションのネットワーク トラフィックの向きと流れは、相互作用の種類 (ピアツーピア、マルチパーティ) によって、およびコンテンツ共有と音声/ビデオの使用に応じて、異なります。 接続元と接続先のポートについて特に注意しながら、ポートとプロトコルのリストを確認して開く必要があります。 たとえば、音声トラフィックは 20 個のポート (50000 から 50019 までの TCP/UDP) をクライアント側で使用しますが、送信先のポートがサービス側で 10000 個のポートの範囲内 (50000 から 59999 までの TCP/UDP) にある可能性があります。送信先のポートには、ファイアウォール上の開いている TCP 443 と UDP 3478 も含まれます。

Skype for Business Online をサポートするために追加のネットワーク構成が必要になる可能性もあります。


## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>Skype for Business 用に最適化された電話機およびデバイスを使用する

リアルタイム メディア セッションでは、ヘッドセットや Web カメラなどの参加者全員が使用するメディア デバイスは、オーディオとビデオの全体的な品質に大きく影響します。 デバイス ドライバーが正しくない低品質のデバイスやデバイスでは、オーディオの全体的な音質が低下し、ビデオの画質が低下します。 一方、認定デバイスまたは高品質なデバイスは、エコー キャンセル、ノイズ フィルタリング、ビデオ解像度、遅延低減に役立ちます。

電話機とデバイスによって、エンド ユーザーの音声とビデオの品質に大きな違いが生じます。Skype for Business 認定プログラムは「Lync 互換」プログラムが発展したもので、デバイスが音声とビデオに関する Microsoft 標準に適合しているかを検証します。数多くの IP 電話、USB オーディオとビデオ デバイス、PC、および会議室が Microsoft によりテストされ、認定されています。お客様は Skype for Business 用に最適化されたデバイスのリストを確認して、ご自身および組織のエンド ユーザーのさまざまなニーズと個人設定に合わせて異なるデバイスを用意するよう努める必要があります。

サポートされている認定済みデバイスの詳細については、次をご覧ください。  

- [Skype for Business Online で使う電話を入手する](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)

- [Skype for Business の電話とデバイス](../../SfbPartnerCertification/certification/devices-ip-phones.md)

- [個人用周辺機器のソリューション カタログ](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

- [Microsoft Lync で認定済みの電話とデバイス](../../SfbPartnerCertification/lync-cert/ip-phones.md)

ユーザーが会議を行い、オーディオ デバイスとビデオ デバイスを使用する環境と周辺領域は、オーディオとビデオの品質のもう 1 つの要因です。ノイズのある環境から通話しているユーザーのオーディオは、エコーがかかり、こもっていて、不明瞭です。暗くて照明が不十分な環境にいるユーザーは、ビデオで明るくクリアな画質を実現することができません。会議室の設定で、マイクとビデオ デバイスの場所は、参加者が受信する音声と画像の品質に直接影響します。

ユーザーのオーディオとビデオのエクスペリエンスのより明確な画像を取得するには、Skype for Business アプリのツールオプション オーディオ デバイスまたはビデオ デバイスを使用して、使用されているデバイスを変更し、設定をカスタマイズします。  >    >    [通話品質の確認] をクリックして、通話の音声 **品質を確認できます**。 If they click **Check Call Quality**, they can then report the quality and issues found with the test call.

![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)

## <a name="related-topics"></a>関連トピック

[Skype for Business Online の ExpressRoute および QoS](expressroute-and-qos-in-skype-for-business-online.md)
