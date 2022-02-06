---
title: セキュリティの主な機能は、Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype for Business Serverには、サーバー間認証、役割ベースのアクセス制御、構成データの集中ストレージなど、いくつかのセキュリティ機能が含まれています。
---

# <a name="key-security-features-in-skype-for-business-server"></a>セキュリティの主な機能は、Skype for Business Server
 
Skype for Business Serverには、サーバー間認証、役割ベースのアクセス制御、構成データの集中ストレージなど、いくつかのセキュリティ機能が含まれています。 
  
この記事では、セキュリティの概要をSkype for Business Serverします。 
  
## <a name="key-security-features-in-skype-for-business-server"></a>セキュリティの主なSkype for Business Server

セキュリティは非常に広範なトピックです。 セキュリティは、Skype for Business Serverエコシステムを構成するデータベース、サービス、ハードウェアのすべての機能Skype for Business Server届きます。 この記事では、セキュリティ用に設計Skype for Business Serverの機能の概要を説明します。
  
### <a name="planning-and-design-tools"></a>計画と設計ツール

Skype for Business Serverには、計画と設計を容易にし、コンポーネントを誤って構成する可能性をSkype for Business Serverがあります。 
  
- **トポロジ計画ツールは** 、トポロジ設計プロセスの多くを自動化します。 この結果は、計画ツールからトポロジ ビルダーにエクスポートできます。このツールは、計画ツールを実行している各サーバーをインストールするためにSkype for Business Server。
    
- **トポロジ ビルダーは、** すべての構成情報をサーバーの全体管理ストアに格納します。
    
これらのツールの詳細については、「管理[ツールSkype for Business Server参照してください](../../management-tools/management-tools.md)。
  
### <a name="central-management-store"></a>中央管理ストア

サーバー Skype for Business Server構成データは、サーバーの全体管理ストアの一部です。 サーバーの全体管理ストアは、展開の定義、設定、保守、管理、説明、運用に必要なデータの堅牢でスキーマ化されたストレージSkype for Business Server提供します。 また、CMS はこのデータを検証して構成の一貫性も保証します。 この構成データに対する変更はすべてサーバーの全体管理ストアで行うので、"同期外" の問題はなくなります。 
  
このデータの読み取り専用のコピーは、エッジ サーバーを含めたトポロジ内のすべてのサーバーにレプリケートされます。 レプリケーションは、既定ではネットワーク サービスのコンテキストで実行されるサービスによって管理され、コンピューター上の単純なユーザーの権限とアクセス許可が低下します。 
  
### <a name="server-to-server-authentication"></a>サーバー間認証

このSkype for Business Server、Open Authorization (OAuth) プロトコルを使用してサーバー間で認証を構成できます。 たとえば、2016 Skype for Business Serverを実行しているサーバーで認証を行Microsoft Exchange Serverできます。 OAuth プロトコルを使用すると、Skype for Business ServerとMicrosoft Exchange Serverを信頼できます。 これにより、シームレスな方法で製品を統合できます。 詳細については、「[サーバー間認証 (OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) とパートナー アプリケーションの管理」を参照Skype for Business Server。
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShellベースの管理と Web ベースの管理インターフェイス

Skype for Business Serverコマンド ライン インターフェイスに基Windows PowerShell強力な管理インターフェイスを提供します。 これにはセキュリティを管理するためのコマンドレットが含まれており、ユーザーが簡単にまたは知らないうちにスクリプトを実行できないように、Windows PowerShell のセキュリティ機能が既定で有効になっています。 つまり、セキュリティを最大限に高め、攻撃の手段を減少させるように、ソフトウェアの既定値が自動的に設定されています。 管理のサポートWindows PowerShell詳細については、「Skype for Business Server管理[シェルSkype for Business Server参照してください](../../manage/management-shell.md)。 
  
### <a name="role-based-access-control-rbac"></a>役割ベースのアクセス制御 (RBAC)

Skype for Business Serverロール ベースのアクセス制御 (RBAC) を提供し、高いセキュリティ基準を維持しながら管理タスクを委任できます。 業務上必要な管理権限のみをユーザーに与える "最小限の特権" の原則に従って RBAC を使用することができます。 Skype for Business Serverは、新しい役割を作成する機能と、既存の役割を変更する機能を提供します。 
  
## <a name="network-address-translation-nat"></a>ネットワーク アドレス変換 (NAT)

Skype for Business Server では、エッジ サーバーの内部インターフェイスでのネットワーク アドレス変換 (NAT) の使用はサポートされていませんが、単一の統合エッジ サーバー トポロジと拡張統合エッジ サーバー トポロジの両方に対してネットワーク アドレス変換 (NAT) を実行するルーターまたはファイアウォールの背後に Access Edge サービス、Web 会議エッジ サービス、および A/V Edge サービスの外部インターフェイスを配置できます。 ハードウェア ロード バランサーの背後にある複数のエッジ サーバーでは、NAT を使用できません。 複数のエッジ サーバーが外部インターフェイスで NAT を使用する場合は、ドメイン ネーム システム (DNS) 負荷分散が必要です。 また、DNS 負荷分散を使用すると、エッジ サーバー プール内のエッジ サーバーあたりのパブリック IP アドレスの数を減らします。 詳細については、「エッジ [サーバーのシナリオ」を参照Skype for Business Server](../../plan-your-deployment/edge-server-deployments/scenarios.md)。
  
> [!NOTE]
> Microsoft Office Communications Server 2007 展開がある企業とフェデレーションを行い、企業とフェデレーション企業の間でオーディオ/ビデオを使用する必要がある場合、ポート要件は、展開されているエッジ サーバーの古いバージョンのポート要件になります。 たとえば、フェデレーション パートナーがエッジ サーバーを新しいバージョンにアップグレードするまで、これらの古いバージョンに必要なポート範囲を両方の企業で開くSkype for Business Server。 その時点で、ポート要件を確認し、新しい構成に応じて減少できます。 
  
## <a name="simplified-certificates-for-edge-servers"></a>エッジ サーバーの簡易証明書

展開ウィザードはサブジェクト名 (SN) およびサブジェクト代替名 (SAN) を自動的に読む込むことができるため、不要で、安全でない可能性があるエントリを含める危険性が減少します。
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>信頼できるコンピューティング セキュリティ開発ライフサイクル (SDL)

Skype for Business Serverは、[Microsoft Trustworthy Computing Security Development Lifecycle](/previous-versions/ms995349(v=msdn.10)) (SDL) に準拠して設計および開発されています。
  
- **デザインによって信頼できる** より安全な統合コミュニケーション システムを作成する最初のステップは、脅威モデルを設計し、設計時に各機能をテストする方法でした。 さらに、Microsoft は、予期しない製品動作に起因するセキュリティの脆弱性を見つけるために、設計された動作の外部でテストを実行します。 複数のセキュリティ関連の改善点がコーディング プロセスとコーディング手法に組み込まれました。 コードが最終的な製品にチェックインされる前に、ビルド時ツールにより、バッファー オーバーランおよびその他のセキュリティ脅威の可能性を検出します。 もちろん、すべての未知のセキュリティ脅威を防ぐように設計することは不可能です。 完全なセキュリティを保証できるシステムはありません。 ただし、製品開発は最初から安全な設計原則を取り入れたため、Skype for Business Serverはアーキテクチャの基本的な部分として業界標準のセキュリティ テクノロジを組み込んでいます。
    
- **既定で信頼できる** 既定では、ネットワーク通信は暗号化Skype for Business Serverされます。 すべてのサーバーは証明書と Kerberos 認証、TLS、Secure Real-Time トランスポート プロトコル (SRTP)、および 128 ビット高度暗号化標準 (AES) 暗号化を含む他の業界標準の暗号化手法を使用します。事実上すべての Skype for Business Server データがネットワーク上で保護されます。 さらに、役割ベースのアクセス制御を使用すると、Skype for Business Server を実行するサーバーを展開して、各サーバーの役割がサービスのみを実行し、それらのサービスに関連するアクセス許可のみをサーバーの役割に適したアクセス許可で実行できます。
    
- **展開によって信頼できる** すべてのSkype for Business Serverには、展開に最適なセキュリティ レベルを決定して構成し、既定以外のオプションをアクティブ化するセキュリティ リスクを評価するためのベスト プラクティスと推奨事項が含まれています。
