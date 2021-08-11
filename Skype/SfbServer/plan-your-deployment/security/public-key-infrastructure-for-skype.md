---
title: パブリック キー インフラストラクチャ Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype for Business Serverは、サーバー認証の証明書に依存し、クライアントとサーバー間、および異なるサーバーの役割間で一つの信頼を確立します。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、および Windows Server 2008 公開キー 基盤 (PKI) は、この信頼チェーンを確立および検証するためのインフラストラクチャを提供します。
ms.openlocfilehash: 7b955aa07143cead900a0140ac8ee64fa02ba34ed3945553e376123c7260909d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329491"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>パブリック キー インフラストラクチャ Skype for Business Server
 
Skype for Business Serverは、サーバー認証の証明書に依存し、クライアントとサーバー間、および異なるサーバーの役割間で一つの信頼を確立します。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、および Windows Server 2008 公開キー 基盤 (PKI) は、この信頼チェーンを確立および検証するためのインフラストラクチャを提供します。
  
証明書とはデジタル ID です。 証明書は、名前によってサーバーを識別し、そのプロパティを指定します。 証明書の情報が有効な場合、証明書は、サーバーに接続するクライアントまたは他のサーバーによって信頼されている CA によって発行される必要があります。 サーバーがプライベート ネットワーク上の他のクライアントおよびサーバーとのみ接続する場合は、CA はエンタープライズ CA で問題ありません。 サーバーがプライベート ネットワーク外のエンティティと対話する場合は、パブリック CA が必要な可能性があります。
  
証明書の情報が有効であっても、証明書を提示しているサーバーが、実際に証明書によって提示されているサーバーであることを確認する手段が必要です。ここで Windows PKI が役立ちます。
  
各証明書は、公開キーにリンクされています。証明書で名前が指定されているサーバーには、そのサーバーのみが知る、対応する秘密キーがあります。接続しようとしているクライアントまたはサーバーは、公開キーを使用して無作為な情報の断片を暗号化し、それをサーバーに送信します。サーバーがその情報を復号化し、プレーン テキストに戻すと、接続しようとしているエンティティは、証明書の秘密キーをサーバーが保持していること、つまり、そのサーバーが証明書で指定されていることを確認できます。
  
> [!NOTE]
> すべてのパブリック CA が証明書の要件に準拠Skype for Business Serverではありません。 認定されているパブリック CA ベンダーの一覧を参照して、パブリック証明書のニーズに合ったベンダーを探すことをお勧めします。 詳細については [、「Unified Communications Certificate Partners」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=140898)。 
  
## <a name="crl-distribution-points"></a>CRL 配布ポイント

Skype for Business Server、すべてのサーバー証明書に 1 つ以上の証明書失効リスト (CRL) 配布ポイントが含まれている必要があります。 CRL 配布ポイント (CDP) は、証明書が発行され、証明書がまだ有効期間内に残っている証明書が失効していないかを確認するために、CRL をダウンロードできる場所です。 CRL 配布ポイントは、証明書のプロパティに URL として示され、通常はセキュリティで保護された HTTP です。
  
## <a name="enhanced-key-usage"></a>拡張キーの使用法

Skype for Business Server認証のために、拡張キー使用法 (EKU) をサポートするには、すべてのサーバー証明書が必要です。 サーバー認証用に EKU フィールドを構成すると、証明書はサーバーを認証する目的で有効になります。 この EKU は MTLS に不可欠です。 EKU に複数のエントリを含め、複数の目的で証明書を有効にできます。
  

