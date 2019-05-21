---
title: Skype for Business Server の主要なセキュリティ機能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype for Business Server には、サーバー間認証、役割ベースのアクセス制御、構成データの一元ストレージなど、いくつかのセキュリティ機能が含まれています。
ms.openlocfilehash: cd86d1ac404cd2fe487f6f9369cc73df0d72c52f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296890"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Skype for Business Server の主要なセキュリティ機能
 
Skype for Business Server には、サーバー間認証、役割ベースのアクセス制御、構成データの一元ストレージなど、いくつかのセキュリティ機能が含まれています。 
  
この記事では、Skype for Business Server のセキュリティについて概要を説明します。 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Skype for Business Server の主要なセキュリティ機能

セキュリティは非常に広い範囲に及ぶトピックです。 Skype for Business Server のすべての機能のほか、Skype for business Server エコシステムを構成するデータベース、サービス、ハードウェアにもセキュリティが設定されます。 この記事では、セキュリティのために設計された Skype for Business Server の一部の機能について説明します。
  
### <a name="planning-and-design-tools"></a>計画ツールと設計ツール

Skype for Business Server には2つのツールが用意されており、計画と設計を容易にして、Skype for Business Server コンポーネントの構成ミスを防ぐことができます。 
  
- **トポロジ計画ツール**は、トポロジ設計プロセスの大部分を自動化します。 計画ツールからトポロジビルダーに結果をエクスポートすることができます。これは、Skype for Business Server を実行している各サーバーをインストールするために必要なツールです。
    
- **トポロジ ビルダー**は、すべての構成情報を中央管理ストアに格納します。
    
これらのツールの詳細については、「 [Skype For Business Server 管理ツール](../../management-tools/management-tools.md)」を参照してください。
  
### <a name="central-management-store"></a>中央管理ストア

Skype for Business Server では、サーバーとサービスに関する構成データは中央管理ストアに含まれています。 中央管理ストアでは、Skype for Business Server の展開を定義、セットアップ、管理、管理、説明、操作するために必要なデータの堅牢な schematized ストレージを提供します。 また、データを検証して構成の一貫性を保ちます。 この構成データに対するすべての変更は、中央管理ストアで行われるため、"非同期" の問題が解消されます。 
  
データの読み取り専用コピーは、エッジ サーバーや存続可能ブランチ アプライアンスなど、トポロジ内のすべてのサーバーにレプリケートされます。レプリケーションは、既定では、ネットワーク サービスのコンテキストで実行されるサービスが管理し、権限とアクセス許可が抑えられてコンピューター上の一般ユーザーと同じになります。 
  
### <a name="server-to-server-authentication"></a>サーバー間認証

Skype for Business Server では、Open Authorization (OAuth) プロトコルを使用してサーバー間で認証を構成することができます。 たとえば、Microsoft Exchange Server 2016 を実行しているサーバーで認証されるように、Skype for Business Server を構成することができます。 OAuth プロトコルを使用すると、Skype for Business Server と Microsoft Exchange Server が相互に信頼できます。 これにより、製品をシームレスな方法で統合することができます。 詳細については、「 [Skype For Business server でサーバー間認証 (OAuth) とパートナーアプリケーションを管理](../../manage/authentication/server-to-server-and-partner-applications.md)する」を参照してください。
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell ベースの管理と Web ベースの管理インターフェイス

Skype for Business Server は、Windows PowerShell コマンドラインインターフェイスに基づいて構築された強力な管理インターフェイスを提供します。 このインターフェイスにはセキュリティを管理するためのコマンドレットが含まれているうえ、Windows PowerShell のセキュリティ機能が既定で有効になっており、ユーザーが簡単にまたは知らないうちにスクリプトを実行することができないようになっています。 つまり、セキュリティを最大限に高め、攻撃の手段を減らすように、ソフトウェアの既定値が自動的に設定されています。 Skype for Business Server での Windows PowerShell 管理のサポートについて詳しくは、「Skype for business [Server 管理シェル](../../manage/management-shell.md)」をご覧ください。 
  
### <a name="role-based-access-control-rbac"></a>役割ベースのアクセス制御 (RBAC)

Skype for Business Server では、役割ベースのアクセス制御 (RBAC) を利用して、セキュリティの高い標準を維持しながら管理タスクを委任することができます。 そのため、業務上必要な管理権限のみをユーザーに与える "最小限の特権" の原則に従って RBAC を使用することができます。 Skype for Business Server では、新しい役割を作成し、既存の役割を変更することもできます。 
  
## <a name="network-address-translation-nat"></a>ネットワーク アドレス変換 (NAT)

Skype for Business Server は、エッジサーバーの内部インターフェイスでのネットワークアドレス変換 (NAT) の使用をサポートしていませんが、アクセスエッジサービス、Web 会議エッジサービス、および A/V Edge サービスの外部インターフェイスの配置をサポートしています。ネットワークアドレス変換 (NAT) を実行するルーターまたはファイアウォールの背後で、統合されたエッジサーバートポロジの1つとスケーリングの両方に対応しています。 ハードウェア ロード バランサーの背後にある複数のエッジ サーバーでは、NAT を使用できません。 複数のエッジ サーバーの外部インターフェイスで NAT を使用する場合は、ドメイン ネーム システム (DNS) の負荷分散が必要です。 DNS 負荷分散を使用すると、エッジ サーバー プール内のエッジ サーバーあたりのパブリック IP アドレスの数を削減できます。 詳細については、「 [Skype For Business Server のエッジサーバーのシナリオ](../../plan-your-deployment/edge-server-deployments/scenarios.md)」を参照してください。
  
> [!NOTE]
> Microsoft Office Communications Server 2007 が展開されているエンタープライズとフェデレーションを行うときに、使用しているエンタープライズとフェデレーション先のエンタープライズとの間で音声ビデオを使用する必要がある場合、ポート要件は、展開されているエッジ サーバーのうち、古い方のバージョン用の要件になります。 たとえば、これらの古いバージョンに必要なポート範囲は、フェデレーションパートナーがそのエッジサーバーを Skype for Business Server にアップグレードするまで両方のエンタープライズで開く必要があります。 アップグレード後には、ポート要件を見直して、新しい構成に応じて削減できます。 
  
## <a name="simplified-certificates-for-edge-servers"></a>エッジ サーバーの簡単化された証明書

展開ウィザードは、サブジェクト名 (SN) やサブジェクト代替名 (SAN) を自動的に読む込むことができるので、安全ではない可能性のある不要なエントリを含める危険性が減少します。
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>信頼できるコンピューティングのセキュリティ開発ライフサイクル (SDL)

Skype for Business Server は、 [Microsoft の信頼できるコンピューティングセキュリティ開発ライフサイクル](https://go.microsoft.com/fwlink/p/?linkid=68761)(SDL) に準拠して設計および開発されています。
  
- **信頼できる設計**より安全なユニファイドコミュニケーションシステムを作成するための最初の手順は、脅威モデルを設計し、設計された各機能をテストすることでした。 Microsoft では加えて、設計動作以外でのテストも実施して、予期しない製品動作から生じるセキュリティ脆弱性を探しています。 コーディング プロセスとコーディング手法には、セキュリティに関連する複数の改善点が組み込まれていました。 ビルド時に使われるツールは、製品にコードが最終的にチェックインされる前にバッファ オーバーランなどの潜在的なセキュリティ上の脅威を検出します。 それでも、未知のセキュリティ上の脅威のすべてを防ぐように設計することは不可能です。 完全なセキュリティを保証できるシステムはありません。 ただし、製品の開発には、最初からのセキュリティで保護された設計原則が採用されているため、Skype for Business Server は、アーキテクチャの基礎部分として業界標準セキュリティ技術を備えています。
    
- **既定で信頼できる**場合既定では、Skype for Business Server のネットワーク通信が暗号化されています。 すべてのサーバーでは、証明書と Kerberos 認証、TLS、セキュリティで保護されたリアルタイムトランスポートプロトコル (SRTP)、およびその他の業界標準の暗号化技法 (128 ビット Advanced Encryption Standard (AES) 暗号化など) が使用されているため、ほぼすべての Skype forBusiness Server データはネットワーク上で保護されています。 さらに、役割ベースのアクセス制御によって、Skype for Business Server を実行しているサーバーを展開して、各サーバーの役割がサービスのみを実行し、サーバーの役割に対応したアクセス許可のみを持つようにすることができます。
    
- **展開により信頼できる**すべての Skype for Business Server のドキュメントには、展開に最適なセキュリティレベルを決定して構成し、既定以外のオプションをアクティブ化する場合のセキュリティリスクを評価するためのベストプラクティスと推奨事項が含まれています。
    

