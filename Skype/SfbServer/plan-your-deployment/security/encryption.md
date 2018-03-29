---
title: Skype for Business Server 2015 の暗号化
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/15/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: ビジネス サーバー 2015 の Skype は、インスタント メッセージの暗号化に TLS および MTLS を使用します。 トラフィックが内部ネットワークに限定されているか、内部ネットワークの境界を越えるかに関係なく、MTLS は、サーバー間のすべてのトラフィックに必要です。 Skype をビジネス サーバー 2015 のサード パーティ製の IPPBX システムまたは SIP トランクの TLS 接続があるとき省略可能ですが、仲介サーバーとメディア ゲートウェイの間で強く推奨されます。 この接続に TLS を構成する場合は MTLS も必要です。 そのため、ゲートウェイは、仲介サーバーによって信頼されている CA から証明書を構成しなければなりません。
ms.openlocfilehash: bf17f2c8ff8180fa5622957c665da3f4608ca833
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="encryption-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 の暗号化
 
ビジネス サーバー 2015 の Skype は、インスタント メッセージの暗号化に TLS および MTLS を使用します。 トラフィックが内部ネットワークに限定されているか、内部ネットワークの境界を越えるかに関係なく、MTLS は、サーバー間のすべてのトラフィックに必要です。 Skype をビジネス サーバー 2015 のサード パーティ製の IPPBX システムまたは SIP トランクの TLS 接続があるとき省略可能ですが、仲介サーバーとメディア ゲートウェイの間で強く推奨されます。 この接続に TLS を構成する場合は MTLS も必要です。 そのため、ゲートウェイは、仲介サーバーによって信頼されている CA から証明書を構成しなければなりません。
  
> [!NOTE]
> SSL 3.0 に関するセキュリティ アドバイザリが 2014 年に公開されました。 ビジネス サーバー 2015 の Skype で SSL 3.0 を無効にすることは、サポートされているオプションです。 セキュリティ アドバイザリに関する詳細については、 [Lync Server 2013 とビジネス サーバー 2015 の Skype で SSL 3.0 を無効にする](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)を参照してください。 
  
> [!セキュリティに関する注意の最も強力な暗号化プロトコルのことを確認する] を使用すると、ビジネス サーバー 2015 の Skype では、クライアントを TLS 暗号化プロトコルを次の順序でが、: **TLS 1.2、TLS 1.1、TLS 1.0**です。 TLS は、Skype のビジネス サーバー 2015 の重要な側面と、サポートされている環境を維持するために必要なためです。 
  
次の表に、各種トラフィックのプロトコル要件をまとめます。 
  
**トラフィックの保護**

|**トラフィックの種類**|**によって保護されています。**|
|:-----|:-----|
|サーバー間  <br/> |MTLS  <br/> |
|クライアントからサーバー  <br/> |TLS  <br/> |
|インスタント メッセージングとプレゼンス  <br/> |TLS  <br/> |
|オーディオとビデオ、メディアのデスクトップ共有  <br/> |SRTP  <br/> |
|デスクトップ共有 (シグナリング)  <br/> |TLS  <br/> |
|Web 会議  <br/> |TLS  <br/> |
|会議コンテンツのダウンロード、アドレス帳のダウンロード、配布グループの拡張  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>メディアの暗号化

メディア トラフィックは、Secure RTP (SRTP) を使用して暗号化されます。これは、秘密保持機能、認証、RTP トラフィックなどに対する再生攻撃からの保護機能を提供するリアルタイム転送プロトコル (RTP) のプロファイルです。さらに、仲介サーバーとその次のホップ間で双方向にやりとりされるメディアも SRTP を使用して暗号化されます。仲介サーバーとメディア ゲートウェイ間で双方向にやりとりされるメディアはオプションで暗号化され、暗号化することが推奨されます。仲介サーバーはメディア ゲートウェイに対する暗号化をサポートできますが、ゲートウェイは MTLS および証明書のストレージをサポートする必要があります。
  
> [!NOTE]
> ハイブリッド環境を実装する場合も、Skype ビジネス サーバー 2015 の暗号化レベルを変更する必要があります。 既定では、暗号化レベルは "必須" です。 ビジネス サーバー管理シェルには、Skype を使用して、サポートされているにこの設定を変更する必要があります。 ハイブリッドを設定する方法の詳細については、展開に関するドキュメントで[ビジネス上でオンラインに設置型の Skype のユーザーの移動](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md)を参照してください。
  
## <a name="fips"></a>FIPS

システムの FIPS 140-2 のアルゴリズムを使用するのには、Windows サーバー オペレーティング システムが構成されている場合に、連邦情報処理規格 (FIPS) 140-2 のアルゴリズムをサポートして Skype ビジネス サーバー 2015、2016 の Microsoft Exchange Server の動作します。暗号化します。 FIPS のサポートを実装するには、サポートするようにサーバー 2015 のビジネス用の Skype を実行する各サーバーを構成しなければなりません。
  

