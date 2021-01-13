---
title: Skype for Business Server の公開キー基盤
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
description: Skype for Business Server は、証明書を使用してサーバー認証を行い、クライアントとサーバー間、および異なるサーバーの役割間の信頼チェーンを確立します。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、および Windows Server 2008 公開キー基盤 (PKI) は、この信頼チェーンを確立および検証するためのインフラストラクチャを提供します。
ms.openlocfilehash: 3ee9411b5a9259ba7c66c46bf657bb5ee43ab52e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832147"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Skype for Business Server の公開キー基盤
 
Skype for Business Server は、証明書を使用してサーバー認証を行い、クライアントとサーバー間、および異なるサーバーの役割間の信頼チェーンを確立します。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、および Windows Server 2008 公開キー基盤 (PKI) は、この信頼チェーンを確立および検証するためのインフラストラクチャを提供します。
  
証明書とはデジタル ID です。 証明書は、名前によってサーバーを識別し、そのプロパティを指定します。 証明書の情報が有効な場合は、サーバーに接続するクライアントまたは他のサーバーによって信頼されている CA が証明書を発行する必要があります。 サーバーがプライベート ネットワーク上の他のクライアントおよびサーバーとのみ接続する場合は、CA はエンタープライズ CA で問題ありません。 サーバーがプライベート ネットワーク外のエンティティと対話する場合は、パブリック CA が必要な可能性があります。
  
証明書の情報が有効であっても、証明書を提示しているサーバーが、実際に証明書によって提示されているサーバーであることを確認する手段が必要です。ここで Windows PKI が役立ちます。
  
各証明書は、公開キーにリンクされています。証明書で名前が指定されているサーバーには、そのサーバーのみが知る、対応する秘密キーがあります。接続しようとしているクライアントまたはサーバーは、公開キーを使用して無作為な情報の断片を暗号化し、それをサーバーに送信します。サーバーがその情報を復号化し、プレーン テキストに戻すと、接続しようとしているエンティティは、証明書の秘密キーをサーバーが保持していること、つまり、そのサーバーが証明書で指定されていることを確認できます。
  
> [!NOTE]
> すべてのパブリック CA が Skype for Business Server 証明書の要件に準拠している場合ではありません。 認定されているパブリック CA ベンダーの一覧を参照して、パブリック証明書のニーズに合ったベンダーを探すことをお勧めします。 詳細については [、「Unified Communications Certificate Partners」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=140898)。 
  
## <a name="crl-distribution-points"></a>CRL 配布ポイント

Skype for Business Server では、すべてのサーバー証明書に 1 つ以上の証明書失効リスト (CRL) 配布ポイントが含まれている必要があります。 CRL 配布ポイント (CDP) は、証明書が発行されて有効期間内に証明書が失効していないか確認するために、CRL をダウンロードできる場所です。 CRL 配布ポイントは、証明書のプロパティに URL として示され、通常はセキュリティで保護された HTTP です。
  
## <a name="enhanced-key-usage"></a>拡張キー使用法

Skype for Business Server では、サーバー認証の目的で、拡張キー使用法 (EKU) をサポートするためにすべてのサーバー証明書が必要です。 サーバー認証用に EKU フィールドを構成すると、証明書はサーバーを認証する目的で有効になります。 この EKU は MTLS に不可欠です。 EKU に複数のエントリを含め、複数の目的に対して証明書を有効にできます。
  

