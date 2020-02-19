---
title: Lync Server 2013 証明書インフラストラクチャの要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dd1aa5bdde1c94e3d0558be14c67cf62ec8142a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 の証明書インフラストラクチャ要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-06-23_

Lync Server 2013 は、TLS および相互 TLS (MTLS) 接続をサポートするために公開キー基盤 (PKI) を必要とします。

Lync Server は、次の目的で証明書を使用します。

  - クライアントとサーバー間の TLS 接続

  - サーバー間の MTLS 接続

  - パートナーの自動 DNS 検出を使用するフェデレーション

  - インスタント メッセージング (IM) 用のリモート ユーザー アクセス

  - 音声/ビデオ (A/V) セッション、アプリケーション共有、および会議への外部ユーザー アクセス

  - Web サービスの自動検出を使用するモバイル要求

Lync Server では、次の一般的な要件が適用されます。

  - すべてのサーバー証明書がサーバーの承認 (サーバー EKU) をサポートしている必要がある。

  - すべてのサーバー証明書に CRL 配布ポイント (CDP) を含める必要がある。

  - すべての証明書は、オペレーティングシステムでサポートされている署名アルゴリズムを使用して署名する必要があります。 Lync Server 2013 では、ダイジェストサイズ (224、256、384、および512ビット) の SHA-1 および SHA-1 スイートがサポートされており、オペレーティングシステムの要件を満たしているか、それを超えています。 オペレーティングシステムのサポートについ[https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002)ては、「」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > RSASSA-PSS 署名アルゴリズムを使用することはサポートされていません。その他の問題の中では、ログイン時にエラーが発生し、転送の問題が発生する可能性があります。

    
    </div>

  - Lync Server を実行している内部サーバーでは、自動登録がサポートされています。

  - Lync Server エッジサーバーでは、自動登録がサポートされていません。

  - Windows Server 2003 の CA に対して Web ベースの証明書要求を送信する場合は、Windows Server 2003 (SP2 適用済み) または Windows XP を実行しているコンピューターから送信する必要があります。
    
    KB922706 は、Windows Server 2003 証明書サービスの Web 登録について Web 証明書の登録に関わる問題解決をサポートしますが、Windows Server 2008、Windows Vista、または Windows 7 を使用して、Windows Server 2003 CA から証明書を要求できるようにはなりません。

  - 1024、2048、4096の暗号化キーの長さがサポートされています。 2048以上のキーの長さは推奨されています。

  - 既定のダイジェスト、つまりハッシュ署名は RSA です。 ECDH\_P256、ecdh\_P384、および ecdh\_P521 の各アルゴリズムもサポートされています。 

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 での外部ユーザーアクセスの証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Lync Server 2013 の常設チャットサーバーの証明書要件](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Lync Server 2013 でのモビリティの証明書要件](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

