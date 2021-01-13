---
title: Skype for Business Server の主要なセキュリティ機能
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
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype for Business Server には、サーバー間認証、役割ベースのアクセス制御、構成データの集中ストレージなど、いくつかのセキュリティ機能が含まれています。
ms.openlocfilehash: 1163216f2aeb369576f51af53180297f8028813e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832177"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Skype for Business Server の主要なセキュリティ機能
 
Skype for Business Server には、サーバー間認証、役割ベースのアクセス制御、構成データの集中ストレージなど、いくつかのセキュリティ機能が含まれています。 
  
この記事では、Skype for Business Server のセキュリティの概要について説明します。 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Skype for Business Server の主要なセキュリティ機能

セキュリティは非常に広範なトピックです。 セキュリティは、Skype for Business Server のエコシステムを構成するデータベース、サービス、ハードウェアだけでなく、Skype for Business Server のすべての機能に及びます。 この記事では、特にセキュリティを目的として設計された Skype for Business Server の機能の一部について説明します。
  
### <a name="planning-and-design-tools"></a>計画ツールとデザイン ツール

Skype for Business Server には、計画と設計を容易にし、Skype for Business Server コンポーネントを誤って構成する可能性を減らす 2 つのツールが備まれています。 
  
- **トポロジ計画ツールは** 、トポロジ設計プロセスの多くを自動化します。 計画ツールの結果は、Skype for Business Server を実行する各サーバーをインストールするために必要なツールであるトポロジ ビルダーにエクスポートできます。
    
- **トポロジ ビルダーは** 、すべての構成情報を中央管理ストアに格納します。
    
これらのツールの詳細については [、「Skype for Business Server Management Tools」を参照してください](../../management-tools/management-tools.md)。
  
### <a name="central-management-store"></a>中央管理ストア

Skype for Business Server では、サーバーとサービスに関する構成データは中央管理ストアの一部です。 中央管理ストアは、Skype for Business Server 展開の定義、設定、保守、管理、説明、操作に必要なデータの、堅牢でスキーマ化されたストレージを提供します。 また、CMS はこのデータを検証して構成の一貫性も保証します。 この構成データに対する変更はすべて中央管理ストアで行うので、"同期が切れ" の問題がなくなります。 
  
このデータの読み取り専用のコピーは、エッジ サーバーを含めたトポロジ内のすべてのサーバーにレプリケートされます。 レプリケーションは、既定でネットワーク サービスのコンテキストで実行されるサービスによって管理され、コンピューター上の単純なユーザーの権限とアクセス許可が低下します。 
  
### <a name="server-to-server-authentication"></a>サーバー間認証

Skype for Business Server では、OAuth (Open Authorization) プロトコルを使用して、サーバー間で認証を構成できます。 たとえば、Skype for Business Server が 2016 年 1 月 2016 日に実行されているサーバーで認証Microsoft Exchange Serverできます。 OAuth プロトコルを使用すると、Skype for Business Server と Microsoft Exchange Server互いに信頼できます。 これにより、シームレスな方法で製品を統合できます。 詳細については [、「Skype for Business Server でのサーバー間認証 (OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md)およびパートナー アプリケーションの管理」を参照してください。
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShellベースの管理と Web ベースの管理インターフェイス

Skype for Business Server は、新しいコマンド ライン インターフェイスに基Windows PowerShell管理インターフェイスを提供します。 これにはセキュリティを管理するためのコマンドレットが含まれており、ユーザーが簡単にまたは知らないうちにスクリプトを実行できないように、Windows PowerShell のセキュリティ機能が既定で有効になっています。 つまり、セキュリティを最大限に高め、攻撃の手段を減少させるように、ソフトウェアの既定値が自動的に設定されています。 Skype for Business Server Windows PowerShell管理サポートの詳細については [、「Skype for Business Server Management Shell」を参照してください](../../manage/management-shell.md)。 
  
### <a name="role-based-access-control-rbac"></a>役割ベースのアクセス制御 (RBAC)

Skype for Business Server は、役割ベースのアクセス制御 (RBAC) を提供し、高いセキュリティ基準を維持しながら管理タスクを委任できます。 業務上必要な管理権限のみをユーザーに与える "最小限の特権" の原則に従って RBAC を使用することができます。 Skype for Business Server は、新しい役割を作成する機能と、既存の役割を変更する機能を提供します。 
  
## <a name="network-address-translation-nat"></a>ネットワーク アドレス変換 (NAT)

Skype for Business Server は、エッジ サーバーの内部インターフェイスでのネットワーク アドレス変換 (NAT) の使用をサポートしませんが、単一統合エッジ サーバー トポロジと拡張統合エッジ サーバー トポロジの両方でネットワーク アドレス変換 (NAT) を実行するルーターまたはファイアウォールの背後に、アクセス エッジ サービス、Web 会議エッジ サービス、音声ビデオ エッジ サービスの外部インターフェイスを配置できます。 ハードウェア ロード バランサーの背後にある複数のエッジ サーバーは NAT を使用できません。 複数のエッジ サーバーが外部インターフェイスで NAT を使用する場合は、ドメイン ネーム システム (DNS) 負荷分散が必要です。 さらに、DNS 負荷分散を使用すると、エッジ サーバー プール内のエッジ サーバーごとのパブリック IP アドレスの数を減らできます。 詳細については [、Skype for Business Server のエッジ サーバーのシナリオを参照してください](../../plan-your-deployment/edge-server-deployments/scenarios.md)。
  
> [!NOTE]
> Microsoft Office Communications Server 2007 が展開されている企業とフェデレーションを行い、企業とフェデレーション企業の間で音声ビデオを使用する必要がある場合、ポート要件は展開されているエッジ サーバーの古いバージョンの要件になります。 たとえば、フェデレーション パートナーがエッジ サーバーを Skype for Business Server にアップグレードするまで、これらの古いバージョンに必要なポート範囲を両方の企業で開く必要があります。 その時点で、ポート要件を確認し、新しい構成に応じて減少できます。 
  
## <a name="simplified-certificates-for-edge-servers"></a>エッジ サーバーの簡略化された証明書

展開ウィザードはサブジェクト名 (SN) およびサブジェクト代替名 (SAN) を自動的に読む込むことができるため、不要で、安全でない可能性があるエントリを含める危険性が減少します。
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>信頼性の高いコンピューティングのセキュリティ開発ライフサイクル (SDL)

Skype for Business Server は [、Microsoft Trustworthy Computing Security Development Lifecycle](https://go.microsoft.com/fwlink/p/?linkid=68761) (SDL) に準拠して設計および開発されています。
  
- **設計上の信頼性** より安全な統合コミュニケーション システムを作成するための最初の手順は、脅威モデルを設計し、設計時に各機能をテストでした。 さらに、Microsoft は、予期しない製品動作に起因するセキュリティの脆弱性を見つけるために、設計された動作の外部でテストを実行します。 複数のセキュリティ関連の改善点がコーディング プロセスとコーディング手法に組み込まれました。 コードが最終的な製品にチェックインされる前に、ビルド時ツールにより、バッファー オーバーランおよびその他のセキュリティ脅威の可能性を検出します。 もちろん、すべての未知のセキュリティ脅威を防ぐように設計することは不可能です。 完全なセキュリティを保証できるシステムはありません。 ただし、製品開発は最初からセキュリティで保護された設計原則を取り入れたため、Skype for Business Server にはアーキテクチャの基本部分として業界標準のセキュリティ テクノロジが組み込されています。
    
- **既定で信頼できる** 既定では、Skype for Business Server のネットワーク通信は暗号化されます。 すべてのサーバーは証明書と Kerberos 認証、TLS、Secure Real-Time Transport Protocol (SRTP)、および 128 ビット Advanced Encryption Standard (AES) 暗号化を含むその他の業界標準の暗号化手法を使用します。このため、事実上すべての Skype for Business Server データがネットワーク上で保護されます。 さらに、役割ベースのアクセス制御を使用すると、Skype for Business Server を実行しているサーバーを展開して、各サーバーの役割がサーバーの役割に適したサービスのみを実行し、それらのサービスに関連するアクセス許可のみを持つサーバーを展開できます。
    
- **展開によって信頼できる** すべての Skype for Business Server ドキュメントには、展開に最適なセキュリティ レベルを決定および構成し、既定以外のオプションをアクティブ化する場合のセキュリティ リスクを評価するのに役立つベスト プラクティスと推奨事項が含まれています。
    

