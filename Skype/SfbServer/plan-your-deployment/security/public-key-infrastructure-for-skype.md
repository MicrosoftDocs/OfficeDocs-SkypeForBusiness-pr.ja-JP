---
title: Skype for Business Server の公開キー基盤
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype for Business Server は、サーバー認証には証明書を使用し、クライアントとサーバー間、およびサーバーのさまざまな役割間で信頼のチェーンを確立します。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 公開キー基盤 (PKI) は、この信頼チェーンを確立して検証するためのインフラストラクチャを提供します。
ms.openlocfilehash: 381afce84c1a58d15187547c9cb8fd6f98e84790
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296855"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Skype for Business Server の公開キー基盤
 
Skype for Business Server は、サーバー認証には証明書を使用し、クライアントとサーバー間、およびサーバーのさまざまな役割間で信頼のチェーンを確立します。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 公開キー基盤 (PKI) は、この信頼チェーンを確立して検証するためのインフラストラクチャを提供します。
  
証明書とはデジタル ID です。証明書は、名前によってサーバーを識別し、そのプロパティを指定します。証明書の情報が有効であるためには、サーバーに接続するクライアントやその他のサーバーが信頼する CA から証明書が発行されている必要があります。サーバーがプライベート ネットワーク上の他のクライアントおよびサーバーとのみ接続する場合は、CA はエンタープライズ CA で問題ありません。サーバーがプライベート ネットワーク外のエンティティと対話する場合は、パブリック CA が必要な可能性があります。
  
証明書の情報が有効であっても、証明書を提示しているサーバーが、実際に証明書によって提示されているサーバーであることを確認する手段が必要です。ここで Windows PKI が役立ちます。
  
各証明書は、公開キーにリンクされています。証明書で名前が指定されているサーバーには、そのサーバーのみが知る、対応する秘密キーがあります。接続しようとしているクライアントまたはサーバーは、公開キーを使用して無作為な情報の断片を暗号化し、それをサーバーに送信します。サーバーがその情報を復号化し、プレーン テキストに戻すと、接続しようとしているエンティティは、証明書の秘密キーをサーバーが保持していること、つまり、そのサーバーが証明書で指定されていることを確認できます。
  
> [!NOTE]
> すべてのパブリック Ca が Skype for Business Server 証明書の要件を満たしているわけではありません。 認定されているパブリック CA ベンダーの一覧を参照して、パブリック証明書のニーズに合ったベンダーを探すことをお勧めします。 詳細については、「[ユニファイドコミュニケーションの証明書パートナー](https://go.microsoft.com/fwlink/p/?LinkId=140898)」を参照してください。 
  
## <a name="crl-distribution-points"></a>CRL 配布ポイント

Skype for Business Server では、すべてのサーバー証明書に1つ以上の証明書失効リスト (CRL) 配布ポイントが含まれている必要があります。 CRL 配布ポイント (CDP) とは、証明書の発行後にそれが失効していないこと、および証明書が有効期限内にあることを確認するために、CRL をダウンロードできる場所です。 CRL 配布ポイントは、URL として証明書のプロパティに記述され、通常、セキュア HTTP です。
  
## <a name="enhanced-key-usage"></a>拡張キー使用法

Skype for Business Server では、サーバー認証を目的として、すべてのサーバー証明書で拡張キー使用法 (EKU) をサポートする必要があります。 サーバー認証用に EKU フィールドを構成することは、サーバーの認証に対して、その証明書が有効であることを意味します。 この EKU は、MTLS には不可欠です。 EKU には、複数のエントリを指定し、複数の目的に対して証明書を有効にできます。
  

