---
title: 'Lync Server 2013: 証明書レポートの確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a83167576746d3f90d96658b0dd3d65815f5375
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>Lync Server 2013 で証明書レポートを確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

証明書レポートには、Lync 2013 Server の推奨される展開で必要なすべての証明書が含まれています。 入力されたサブジェクト名とサブジェクトの代替名の計画ツールアカウント。 未編集として残っている既定のテキストは、証明書の要求と発行を担当するチームの潜在的な問題を表している可能性があります。 証明書情報には、証明書の一般的な発行元に関する情報も含まれます。 インフラストラクチャに内部の公開キー基盤 (PKI) が配置されていない場合は、すべての証明書を公開証明書プロバイダーを通じて要求できます。 レポートの拡張キー使用法 (EKU) とフィールドへの割り当ては、各証明書の目的と場所を理解するのに非常に役立ちます。

![証明書管理者レポート](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "証明書管理者レポート")

展開内のそれぞれの証明書の使用法および目的を注意深く確認し、しっかりと理解してください。 証明書の役割についての質問がある場合は、どのサーバーまたはサービスが何を対象としているのかを確認します。 Lync Server 2013 の証明書は、主に次の2つの目的で使用されます。

  - 相互トランスポート層セキュリティ (MTLS) - 通信にかかわっているコンピューターがそれぞれ証明書を提示し、他のコンピューターに対して自分の ID を証明します。これは、サーバー認証として知られています。通信は、それぞれのコンピューターが他のコンピューターの ID を信頼するまで開始されません。

  - 暗号化 ‐ 暗号化 (Secure Sockets Layer (SSL) およびトランスポート層セキュリティ (TLS)) は、セキュリティで保護された通信およびプライバシーの保護を支援し、信頼性の高い通信およびコラボレーション システムを作成するための重要な手段です。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での管理者レポートの確認](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

