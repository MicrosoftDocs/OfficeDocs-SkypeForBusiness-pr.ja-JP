---
title: Skype for Business Server の Active Directory ドメイン サービス
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
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory ドメイン サービスは、Windows Server 2003、Windows Server 2008、Windows Server 2012 R2 ネットワークのディレクトリ サービスWindows Server 2012機能します。 また、Active Directory ドメイン サービスは、Skype for Business Server セキュリティ インフラストラクチャを構築する基盤として機能します。 このセクションの目的は、Skype for Business Server が Active Directory ドメイン サービスを使用して IM、Web 会議、メディア、および音声の信頼できる環境を作成する方法について説明します。 Active Directory ドメイン サービスの環境の準備の詳細については、「展開」のドキュメントの「Skype for Business Server のインストール」を参照してください。 Windows Server のネットワークにおける Active Directory ドメイン サービスの役割の詳細については、お使いのバージョンのオペレーティング システムのドキュメントを参照してください。
ms.openlocfilehash: c4fea392fbabafa0852c21aa5b15118f2427319a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832327"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Skype for Business Server の Active Directory ドメイン サービス
 
Active Directory ドメイン サービスは、Windows Server 2003、Windows Server 2008、Windows Server 2012 R2 ネットワークのディレクトリ サービスWindows Server 2012機能します。 また、Active Directory ドメイン サービスは、Skype for Business Server セキュリティ インフラストラクチャを構築する基盤として機能します。 このセクションの目的は、Skype for Business Server が Active Directory ドメイン サービスを使用して IM、Web 会議、メディア、および音声の信頼できる環境を作成する方法について説明します。 Active Directory ドメイン サービスの環境の準備の詳細については、「展開」のドキュメントの [「Skype for Business Server](../../deploy/install/install.md) のインストール」を参照してください。 Windows Server のネットワークにおける Active Directory ドメイン サービスの役割の詳細については、お使いのバージョンのオペレーティング システムのドキュメントを参照してください。
  
Skype for Business Server は、Active Directory ドメイン サービスを使用して次の情報を保存します。
  
- フォレスト内で Skype for Business Server を実行しているすべてのサーバーで必要なグローバル設定。
    
- フォレスト内で Skype for Business Server を実行しているすべてのサーバーの役割を識別するサービス情報。
    
- 一部のユーザー設定。
    
## <a name="active-directory-infrastructure"></a>Active Directory のインフラストラクチャ

Active Directory のインフラストラクチャ要件には、次のようなものがあります。
  
- ドメイン コントローラーのオペレーティング システム要件
    
- ドメインとフォレストの機能レベルの要件
    
- グローバル カタログ ドメインの要件
    
詳細については [、「Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。
  
## <a name="universal-groups"></a>ユニバーサル グループ

フォレストの準備中に、Skype for Business Server は、グローバル設定とサービスにアクセスして管理するアクセス許可を持つさまざまなユニバーサル グループを Active Directory ドメイン サービス内に作成します。 作成されるユニバーサル グループには、次のようなものがあります。
  
- **管理グループ**。 これらのグループは、Skype for Business Server ネットワークの基本的な管理者の役割を定義します。 フォレストの準備中に、これらの管理者グループが Skype for Business Server インフラストラクチャ グループに追加されます。
    
- **サービス グループ**。 これらのグループは、Skype for Business Server が提供するさまざまなサービスにアクセスするために必要なサービス アカウントです。
    
- **インフラストラクチャ グループ**。 これらのグループは、Skype for Business Server インフラストラクチャの特定の領域にアクセスするためのアクセス許可を提供します。 変更したり、ユーザーを直接追加したりしないでください。 フォレストの準備中に、特定のサービス グループと管理グループが適切なインフラストラクチャ グループに追加されます。
    
AD for Skype for Business Server の準備時に作成される特定のユニバーサル グループ、およびインフラストラクチャ グループに追加されるサービスグループと管理グループの詳細については、「展開」のドキュメントの [「Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) でのフォレストの準備によって行われた変更」を参照してください。
  
> [!NOTE]
> Skype for Business Server は、ドメイン コントローラー用の Windows Server 2012 および Windows Server 2003 オペレーティング システムのユニバーサル グループをサポートします。 ユニバーサル グループのメンバーには、ドメイン ツリーまたはフォレスト内の任意のドメインの他のグループとアカウントを含め、ドメイン ツリーまたはフォレスト内の任意のドメインのアクセス許可を割り当てることができます。 ユニバーサル グループのサポートと管理者の委任を組み合わせると、Skype for Business Server の展開の管理が簡素化されます。 たとえば、あるドメインを別のドメインに追加して、管理者が両方を管理できる必要はありません。 
  
## <a name="role-based-access-control"></a>役割ベースのアクセス制御

ユニバーサル サービス グループと管理グループを作成し、サービス グループと管理グループを適切なユニバーサル グループに追加する以外に、フォレストの準備では、Role-Based アクセス制御 (RBAC) グループも作成されます。 フォレストの準備によって作成される特定の RBAC グループの詳細については、「展開」のドキュメントの [「Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) でのフォレストの準備によって行われた変更」を参照してください。 RBAC グループの詳細については [、Skype for Business Server の役割ベースのアクセス制御 (RBAC) を参照してください](role-based-access-control-rbac.md)。
  
## <a name="access-control-entries-aces-and-inheritance"></a>アクセス制御エントリ (ACE) と継承

フォレストの準備では、プライベート ACE とパブリック ACE の両方が作成され、ユニバーサル グループの ACE が追加されます。 Skype for Business Server で使用されるグローバル設定コンテナーに特定のプライベート ACL を作成します。 このコンテナーは Skype for Business Server でのみ使用され、グローバル設定の保存場所に応じて、ルート ドメインの構成コンテナーまたはシステム コンテナーに格納されます。
  
ドメインの準備ステップでは、ドメイン内のユーザーをホストおよび管理するアクセス許可を与えるアクセス制御エントリ (ACE) をユニバーサル グループに追加します。ドメインの準備で、ドメイン ルートと 3 つの組み込みコンテナー (ユーザー、コンピューター、およびドメイン コントローラー) に対する ACE が作成されます。
  
フォレストの準備とドメインの準備によって作成および追加されたパブリック ACEs の詳細については、「展開」のドキュメントの [「Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) でのフォレストの準備による変更」および [「Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) でのドメインの準備による変更」を参照してください。
  
組織では、セキュリティ リスクを軽減するために Active Directory ドメイン サービス (AD DS) をロックダウンすることがよくあります。 ただし、ロックダウンされた Active Directory 環境では、Skype for Business Server に必要なアクセス許可を制限できます。 たとえば、コンテナーと OU からの ACE の削除や、ユーザー、連絡先、InetOrgPerson、コンピューターの各オブジェクトでのアクセス許可の継承の無効化などが挙げられます。 ロックダウンされた Active Directory 環境では、コンテナーと OU のアクセス許可を必要に応じて手動で設定する必要があります。
  
## <a name="server-information"></a>サーバー情報

ライセンス認証中に、Skype for Business Server は Active Directory ドメイン サービスの次の 3 つの場所にサーバー情報を公開します。
  
- Skype for Business Server がインストールされている物理コンピューターに対応する各 Active Directory コンピューター オブジェクト上のサービス接続ポイント (SCP)。
    
- **msRTCSIP-Pools** クラスのコンテナーに作成されるサーバー オブジェクト。
    
- トポロジ ビルダーで指定された信頼済みサーバー。
    
## <a name="service-connection-points"></a>サービス接続ポイント

Active Directory ドメイン サービスの各 Skype for Business Server オブジェクトには、RTC Services と呼ばれる SCP があります。この SCP には、各コンピューターを識別し、提供するサービスを指定する多数の属性が含まれています。 さらに重要な SCP 属性には、serviceDNSName、serviceDNSNameType、serviceClassname、serviceBindingInformation *があります*。    サードパーティのアセット管理アプリケーションは、これらの SCP 属性や他の SCP 属性に対してクエリを実行することで、展開全体にわたってサーバー情報を取得できます。
  
## <a name="active-directory-server-objects"></a>Active Directory サーバー オブジェクト

各 Skype for Business Server サーバーの役割には、対応する Active Directory オブジェクトがあります。このオブジェクトの属性は、その役割によって提供されるサービスを定義します。 また、Standard Edition サーバーがアクティブ化されている場合、または Enterprise Edition プールが作成されると、Skype for Business Server は **msRTCSIP-Pools** コンテナーに新しい **msRTCSIP-Pool** オブジェクトを作成します。 **msRTCSIP-Pool** クラスは、プールの完全修飾ドメイン名 (FQDN) と、プールのフロントエンド コンポーネントとバック エンド コンポーネントの関連付けを指定します。 (Standard Edition サーバーは論理プールと見なされ、フロントエンドとバック エンドが 1 台のコンピューターに同じ場所に表示されます)。
  
## <a name="trusted-servers"></a>信頼済みのサーバー

Skype for Business Server では、トポロジ ビルダーを実行してトポロジを公開するときに、信頼済みサーバーが指定されます。 公開したトポロジは、すべてのサーバー情報を含めて、中央管理ストアに格納されます。 中央管理ストアで定義されているサーバーのみが信頼されます。 Skype for Business Server では、信頼済みサーバーとは、次の条件を満たすサーバーです。
  
- サーバーの FQDN が、中央管理ストアに格納されているトポロジに出現する。
    
- サーバーが、信頼されている CA からの有効な証明書を提示している。 詳細については [、「Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [System requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。
    
このどちらかの条件が満たされていない場合、サーバーは信頼されず、サーバーとの接続は拒否されます。 この二重要件により、悪意のあるサーバーが有効なサーバーの FQDN を引き継ごう攻撃を防ぐ可能性は低い場合があります。
  
さらに、Microsoft Office Communications Server 2007 R2 および Microsoft Office Communications Server 2007 展開が Skype for Business Server サーバーと通信するために、Skype for Business Server は以前のリリースの信頼済みサーバーのリストを保持するためのフォレストの準備中にコンテナーを作成します。 次の表は、以前の展開との互換性維持のために作成されるコンテナーを示しています。
  
**信頼済みのサーバーのリストと、以前のリリースとの互換性を維持するための Active Directory コンテナー**

|**信頼済みのサーバーのリスト**|**Active Directory コンテナー**|
|:-----|:-----|
|Standard Edition サーバーおよびエンタープライズ プールのフロント エンド サーバー  <br/> |RTC サービス/グローバル設定  <br/> |
|会議サーバー  <br/> |RTC サービス/信頼済み MCU  <br/> |
|Web コンポーネント サーバー  <br/> |RTC サービス/TrustedWebComponentsServers  <br/> |
|仲介サーバーと Communicator Web Access サーバー、アプリケーション サーバー、レジストラーと QoE、音声ビデオ会議サービス (サードパーティの SIP サーバーを含む)  <br/> |RTC サービス/信頼済みサービス  <br/> |
|プロキシ サーバー  <br/> |Skype for Business Server はプロキシ サーバーの下位互換性をサポートしません  <br/> |
   

## <a name="see-also"></a>関連項目

[Skype for Business Server 用の Active Directory の準備](../../deploy/install/prepare-active-directory.md)
