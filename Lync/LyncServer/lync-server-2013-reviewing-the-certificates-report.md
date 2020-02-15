---
title: 'Lync Server 2013: 証明書レポートの確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a01f778e855fc5934b524c5bf4a5829a2ca31e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>Lync Server 2013 の証明書レポートの確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

証明書レポートには、推奨される Lync Server 2013 の展開に必要なすべての証明書が含まれています。 入力されたサブジェクト名とサブジェクトの別名の計画ツールアカウント。 未編集のままになっている既定のテキストは、証明書の要求と発行を担当するチームの潜在的な課題を表している場合があります。 証明書情報には、証明書が主としてどこから発行されるかについての情報も含まれています。 インフラストラクチャが内部公開キー基盤 (PKI) を持たない場合、すべての証明書はパブリック証明書プロバイダーを介して要求することができます。 拡張キー使用法 (EKU) およびレポートの [割り当て] フィールドは、それぞれの証明書の目的および場所を知るのに非常に有用です。

![証明書管理レポート](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "証明書管理レポート")

展開内の各証明書の用途と目的を慎重に確認し、理解していることを確認してください。 証明書の内容についての質問がある場合は、どのサーバーまたはサービスがどのようなものになっているかを確認します。 Lync Server 2013 の証明書は、主に次の2つの目的で使用されます。

  - 相互トランスポート層セキュリティ (MTLS) –通信に関与するコンピューターはそれぞれ、id を証明する証明書を別のコンピューターに提示します。 これは、サーバー認証と呼ばれます。 通信は、各コンピューターが他のコンピューターの id を信頼するまで開始できません。

  - 暗号化 –  暗号化 (Secure Sockets Layer (SSL) およびトランスポート層セキュリティ (TLS)) は、セキュリティで保護された通信およびプライバシーの保護を支援し、信頼性の高い通信およびコラボレーション システムを作成するための重要な手段です。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での管理者レポートの確認](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

