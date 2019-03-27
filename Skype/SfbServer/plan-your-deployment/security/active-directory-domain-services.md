---
title: Skype ビジネス サーバーの active Directory ドメイン サービス
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory ドメイン サービスは、ディレクトリ サービスでは、Windows Server 2003、Windows Server 2008、Windows Server 2012 では、Windows Server 2012 R2 のネットワークとして機能します。 Active Directory ドメイン サービスは、Skype ビジネス サーバーのセキュリティ インフラストラクチャを構築する基盤としても機能します。 このセクションの目的は、IM、Web 会議、メディア、および音声の信頼できる環境を作成する、Skype のビジネス サーバーが Active Directory ドメイン サービスを使用する方法について説明します。 Active Directory ドメイン サービスのお客様の環境を準備する方法の詳細についてを参照してくださいインストール Skype ビジネス サーバーの展開に関するドキュメント。 Windows Server ネットワークで Active Directory ドメイン サービスの役割についての詳細は、使用しているオペレーティング システムのバージョンのドキュメントを参照してください。
ms.openlocfilehash: 1664f3b354078c79429b20e7654b363ce9fccb7f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892386"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Skype ビジネス サーバーの active Directory ドメイン サービス
 
Active Directory ドメイン サービスは、ディレクトリ サービスでは、Windows Server 2003、Windows Server 2008、Windows Server 2012 では、Windows Server 2012 R2 のネットワークとして機能します。 Active Directory ドメイン サービスは、Skype ビジネス サーバーのセキュリティ インフラストラクチャを構築する基盤としても機能します。 このセクションの目的は、IM、Web 会議、メディア、および音声の信頼できる環境を作成する、Skype のビジネス サーバーが Active Directory ドメイン サービスを使用する方法について説明します。 Active Directory ドメイン サービスのお客様の環境を準備する方法の詳細は、展開に関するドキュメントで[ビジネスのサーバー用の Skype のインストール](../../deploy/install/install.md)を参照してください。 Windows Server ネットワークで Active Directory ドメイン サービスの役割についての詳細は、使用しているオペレーティング システムのバージョンのドキュメントを参照してください。
  
ビジネス サーバーの Skype は、格納する Active Directory ドメイン サービスを使用します。
  
- Skype を実行するビジネス サーバーをフォレスト内のすべてのサーバーを必要とするグローバル設定です。
    
- Skype を実行するビジネス サーバーをフォレスト内のすべてのサーバーの役割を識別する情報をサービスします。
    
- 一部のユーザー設定。
    
## <a name="active-directory-infrastructure"></a>Active Directory インフラストラクチャ

Active Directory のインフラストラクチャ要件を以下に示します。
  
- ドメイン コントローラーのオペレーティング システム要件
    
- ドメインとフォレストの機能レベルの要件
    
- グローバル カタログ ドメインの要件
    
詳細については、 [Skype のビジネス サーバー 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)や[ビジネス サーバー 2019 の Skype のサーバーの要件](../../../SfBServer2019/plan/system-requirements.md)を参照してください。
  
## <a name="universal-groups"></a>ユニバーサル グループ

フォレストの準備、Skype ビジネス サーバーにアクセスし、グローバル設定とサービスを管理する権限のある Active Directory ドメイン サービス内のさまざまなユニバーサル グループを作成します。 作成されるユニバーサル グループには、次のようなものがあります。
  
- **管理グループ**です。 これらのグループは、ビジネス サーバー ネットワークでの Skype の根本的な管理者の役割を定義します。 フォレストの準備中には、これらの管理者グループはビジネス サーバー インフラストラクチャ グループの Skype に追加されます。
    
- **サービス グループ**です。 これらのグループは、ビジネスのサーバーに対して、Skype によって提供される、さまざまなサービスへのアクセスに必要なサービス アカウントです。
    
- **インフラストラクチャ グループ**です。 これらのグループは、ビジネスのサーバー インフラストラクチャの Skype の特定の領域にアクセスするアクセス許可を提供します。 変更したり、ユーザーを直接追加したりしないでください。 フォレストの準備時に、特定のサービス グループと管理グループが、対応するインフラストラクチャ グループに追加されます。
    
インフラストラクチャ グループに追加するサービスと管理グループと同様に、Skype の AD を準備する際に作成された特定のユニバーサル グループの詳細については、Skype のビジネスのためのフォレストの準備によって加えられた変更の[を参照してください。サーバー](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)の展開に関するドキュメントです。
  
> [!NOTE]
> ビジネス サーバーの Skype では、ドメイン コント ローラーを Windows Server 2003 オペレーティング システムだけで、Windows Server 2012 では、ユニバーサル グループをサポートしています。 ユニバーサル グループのメンバーは、ドメイン ツリーまたはフォレスト内の他のグループと任意のドメインからのアカウントを含めることができ、ドメイン ツリーまたはフォレスト内のドメインのアクセス許可を割り当てることができます。 ユニバーサル グループのサポート、管理者の委任と組み合わせるには、Skype ビジネス サーバーの展開の管理が容易になります。 たとえば、両方を管理する管理者を有効にする別のドメインを追加する必要はありません。 
  
## <a name="role-based-access-control"></a>役割ベースのアクセス制御

ユニバーサル サービス グループと管理グループを作成し、サービス グループと管理グループを対応するユニバーサル グループに追加することに加えて、フォレストの準備では役割ベースのアクセス制御 (RBAC) グループも作成されます。 フォレストの準備で作成される個々の RBAC グループの詳細については、「展開」のドキュメントの「[Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)」を参照してください。 RBAC グループの詳細については、 [Skype のビジネス サーバーの役割に基づくアクセス制御 (RBAC)](role-based-access-control-rbac.md)を参照してください。
  
## <a name="access-control-entries-aces-and-inheritance"></a>アクセス制御エントリ (ACE) と継承

フォレストの準備では、プライベート ACE とパブリック ACE の両方が作成され、ユニバーサル グループの ACE が追加されます。 Skype によってビジネスのサーバーが使用するグローバル設定コンテナーに特定のプライベート Ace が作成されます。 このコンテナーでは、ビジネスのサーバーの Skype によってのみ使用され、構成コンテナーまたはグローバル設定を保存する場所によって、ルート ドメインのシステム コンテナーであります。
  
ドメインの準備ステップでは、ドメイン内のユーザーをホストおよび管理するアクセス許可を与えるアクセス制御エントリ (ACE) をユニバーサル グループに追加します。ドメインの準備で、ドメイン ルートと 3 つの組み込みコンテナー (ユーザー、コンピューター、およびドメイン コントローラー) に対する ACE が作成されます。
  
パブリック Ace に関する詳細情報が作成され、フォレストの準備とドメインの準備によって追加された、[ビジネス サーバーの Skype でのフォレストの準備によって変更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)しで[Skype のビジネス サーバーでドメインの準備によって変更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md)をを参照してください、。展開に関するドキュメントです。
  
組織は、多くの場合、Active Directory ドメイン サービス (AD DS)、セキュリティ上のリスクを軽減するためをロックします。 ただし、ロック ダウンした Active Directory 環境では、Skype のビジネス サーバーを必要とするアクセス許可を制限できます。 たとえば、コンテナーと OU からの ACE の削除や、ユーザー、連絡先、InetOrgPerson、コンピューターの各オブジェクトでのアクセス許可の継承の無効化などが挙げられます。 ロックされている Active Directory 環境を許可する必要があります手動で設定するのコンテナーおよび Ou を必要とします。
  
## <a name="server-information"></a>サーバー情報

ライセンス認証では、Skype のビジネス サーバーは Active Directory ドメイン サービスの 3 つの次の場所にサーバーの情報を発行します。
  
- サービス接続ポイント (SCP) を使用ビジネス サーバーの Skype がインストールされている物理コンピューターに対応する各 Active Directory のコンピューター オブジェクトにします。
    
- **msRTCSIP-Pools** クラスのコンテナーに作成されるサーバー オブジェクト。
    
- 信頼されたサーバーをトポロジ ビルダーで指定します。
    
## <a name="service-connection-points"></a>サービス接続ポイント

ビジネス サーバー オブジェクトを Active Directory ドメイン サービス内の各 Skype では、RTC サービスは、各コンピューターを識別し、それが提供するサービスを指定する属性の数値が含まれますと呼ばれる、SCP があります。 重要な SCP 属性は*serviceDNSName* 、 *serviceDNSNameType* 、 *serviceClassname* 、および*serviceBindingInformation*があります。 サードパーティの資産管理アプリケーションは、これらおよび他の SCP 属性に対してクエリを実行して、展開の間でサーバー情報を取得できます。
  
## <a name="active-directory-server-objects"></a>サーバーの active Directory オブジェクト

Business Server のサーバー ロールの各 Skype では、その役割が提供するサービスを定義する属性を持つオブジェクトの対応する Active Directory があります。 また、Standard Edition server がアクティブである場合、またはエンタープライズ プールを作成するときは、Skype ビジネス サーバーの**msRTCSIP プール**コンテナーに新しい**msRTCSIP プール**オブジェクトを作成します。 **MsRTCSIP プール**のクラスは、プールのフロント エンドおよびバックエンド ・ コンポーネント間の関係のほかに、プールの完全修飾ドメイン名 (FQDN) を指定します。 (Standard Edition サーバーは、論理プールのフロント エンドとバックエンドの端が 1 台のコンピューターに併設されていると見なされますが)。
  
## <a name="trusted-servers"></a>信頼済みのサーバー

ビジネス サーバーの Skype では、信頼されたサーバーは、トポロジ ビルダーを実行し、トポロジを公開するときに指定されたものです。 公開したトポロジは、すべてのサーバー情報を含めて、中央管理ストアに格納されます。 中央管理ストアで定義されているサーバーのみが信頼されます。 ビジネス サーバーの Skype は、信頼されたサーバーで次の条件を満たすもの。
  
- サーバーの FQDN が、中央管理ストアに格納されているトポロジに出現する。
    
- サーバーが、信頼されている CA からの有効な証明書を提示している。 詳細については、 [Skype のビジネス サーバー 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)や[ビジネス サーバー 2019 の Skype のシステム要件](../../../SfBServer2019/plan/system-requirements.md)を参照してください。
    
このどちらかの条件が満たされていない場合、サーバーは信頼されず、サーバーとの接続は拒否されます。 この二重の要件は、悪意のあるサーバーが有効なサーバーの FQDN を引き継ぐためにしようと可能な場合は、ほとんどの攻撃を防止します。
  
さらに、これらのサーバーの Skype で通信するために Microsoft Office 通信 Server 2007 R2 とマイクロソフトの Office Communications Server 2007 の展開を有効にするには、Skype ビジネス サーバーの作成コンテナー フォレストの準備中に以前のリリース用の信頼されたサーバーのリストを保持します。 次の表は、以前の展開との互換性維持のために作成されるコンテナーを示しています。
  
**以前のリリースとの互換性のためのサーバーのリストと、Active Directory コンテナーの信頼**

|**信頼済みのサーバーのリスト**|**Active Directory コンテナー**|
|:-----|:-----|
|Standard Edition サーバーおよびエンタープライズ プールのフロント エンド サーバー  <br/> |RTC サービス/グローバル設定  <br/> |
|会議サーバー  <br/> |RTC サービス/信頼済み MCU  <br/> |
|Web コンポーネント サーバー  <br/> |RTC サービス/TrustedWebComponentsServers  <br/> |
|仲介サーバーと Communicator Web Access サーバー、アプリケーション サーバー、レジストラーと QoE、音声ビデオ会議サービス (サードパーティの SIP サーバーを含む)  <br/> |RTC サービス/信頼済みサービス  <br/> |
|プロキシ サーバー  <br/> |Skype ビジネス サーバーがプロキシ サーバーの下位互換性をサポートしていません  <br/> |
   

## <a name="see-also"></a>関連項目

[Skype のビジネス サーバーの Active Directory を準備します。](../../deploy/install/prepare-active-directory.md)
