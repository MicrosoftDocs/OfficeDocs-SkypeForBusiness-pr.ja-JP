---
title: Skype for Business Server の Active Directory ドメインサービス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory ドメインサービスは、Windows Server 2003、Windows Server 2008、Windows Server 2012、Windows Server 2012 R2 ネットワークのディレクトリサービスとして機能します。 Active Directory ドメインサービスは、Skype for Business Server のセキュリティインフラストラクチャを構築する基盤としても機能します。 このセクションの目的は、Skype for Business Server で Active Directory ドメインサービスを使って、IM、Web 会議、メディア、音声の信頼できる環境を構築する方法を説明します。 Active Directory ドメインサービスの環境の準備について詳しくは、「展開ドキュメントに Skype for Business Server をインストールする」をご覧ください。 Windows Server ネットワークの Active Directory ドメインサービスの役割の詳細については、使用しているオペレーティングシステムのバージョンのドキュメントを参照してください。
ms.openlocfilehash: ec3a09e2203b6f862d87403818b43ab6daae33ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815715"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Skype for Business Server の Active Directory ドメインサービス
 
Active Directory ドメインサービスは、Windows Server 2003、Windows Server 2008、Windows Server 2012、Windows Server 2012 R2 ネットワークのディレクトリサービスとして機能します。 Active Directory ドメインサービスは、Skype for Business Server のセキュリティインフラストラクチャを構築する基盤としても機能します。 このセクションの目的は、Skype for Business Server で Active Directory ドメインサービスを使って、IM、Web 会議、メディア、音声の信頼できる環境を構築する方法を説明します。 Active Directory ドメインサービスの環境の準備について詳しくは、「展開ドキュメントに[Skype For Business Server をインストール](../../deploy/install/install.md)する」をご覧ください。 Windows Server ネットワークの Active Directory ドメインサービスの役割の詳細については、使用しているオペレーティングシステムのバージョンのドキュメントを参照してください。
  
Skype for Business Server は Active Directory ドメインサービスを使用して保存します。
  
- フォレスト内の Skype for Business Server を実行しているすべてのサーバーが必要とするグローバル設定。
    
- フォレスト内の Skype for Business Server を実行しているすべてのサーバーの役割を特定するサービス情報。
    
- 一部のユーザー設定。
    
## <a name="active-directory-infrastructure"></a>Active Directory インフラストラクチャ

Active Directory のインフラストラクチャ要件には、次のものがあります。
  
- ドメイン コントローラーのオペレーティング システム要件
    
- ドメインとフォレストの機能レベルの要件
    
- グローバル カタログ ドメインの要件
    
詳細については、「 [skype For Business server 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」または「 [Skype for business Server 2019 のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。
  
## <a name="universal-groups"></a>ユニバーサル グループ

フォレストの準備中に、Skype for Business Server は、グローバル設定とサービスにアクセスして管理するためのアクセス許可を持つ、Active Directory ドメインサービス内でさまざまなユニバーサルグループを作成します。 作成されるユニバーサル グループには、次のようなものがあります。
  
- **管理グループ**。 これらのグループは、Skype for Business Server ネットワークの基本的な管理者の役割を定義します。 フォレストの準備中に、これらの管理者グループが Skype for Business Server インフラストラクチャグループに追加されます。
    
- **サービスグループ**。 これらのグループは、Skype for Business Server によって提供されるさまざまなサービスにアクセスするために必要なサービスアカウントです。
    
- **インフラストラクチャグループ**。 これらのグループは、Skype for Business Server インフラストラクチャの特定の領域にアクセスするためのアクセス許可を提供します。 変更したり、ユーザーを直接追加したりしないでください。 フォレストの準備時に、特定のサービス グループと管理グループが、対応するインフラストラクチャ グループに追加されます。
    
Skype for Business Server 用の広告を準備するときに作成される特定のユニバーサルグループ、およびインフラストラクチャグループに追加されるサービスと管理グループの詳細については、展開ドキュメントの「 [Skype For Business Server でのフォレストの準備による変更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)」を参照してください。
  
> [!NOTE]
> Skype for Business Server は、Windows Server 2012 のユニバーサルグループに加えて、ドメインコントローラーの Windows Server 2003 オペレーティングシステムをサポートしています。 ユニバーサルグループのメンバーには、ドメインツリーまたはフォレスト内の任意のドメインの他のグループとアカウントを含めることができ、ドメインツリーまたはフォレスト内の任意のドメインでアクセス許可を割り当てることができます。 ユニバーサルグループのサポートは、管理者の委任と組み合わせることで、Skype for Business Server の展開を簡単に管理できます。 たとえば、あるドメインを別のドメインに追加して、管理者が両方を管理できるようにする必要はありません。 
  
## <a name="role-based-access-control"></a>役割ベースのアクセス制御

ユニバーサル サービス グループと管理グループを作成し、サービス グループと管理グループを対応するユニバーサル グループに追加することに加えて、フォレストの準備では役割ベースのアクセス制御 (RBAC) グループも作成されます。 フォレストの準備で作成される個々の RBAC グループの詳細については、「展開」のドキュメントの「[Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)」を参照してください。 RBAC グループの詳細については、「 [Skype For Business Server の役割ベースのアクセス制御 (RBAC)](role-based-access-control-rbac.md)」を参照してください。
  
## <a name="access-control-entries-aces-and-inheritance"></a>アクセス制御エントリ (ACE) と継承

フォレストの準備では、プライベート ACE とパブリック ACE の両方が作成され、ユニバーサル グループの ACE が追加されます。 Skype for Business Server で使用されるグローバル設定コンテナーに特定のプライベート Ace を作成します。 このコンテナーは、Skype for Business Server でのみ使用され、グローバル設定を保存する場所に応じて、構成コンテナーまたはルートドメイン内のシステムコンテナーにあります。
  
ドメインの準備ステップでは、ドメイン内のユーザーをホストおよび管理するアクセス許可を与えるアクセス制御エントリ (ACE) をユニバーサル グループに追加します。ドメインの準備で、ドメイン ルートと 3 つの組み込みコンテナー (ユーザー、コンピューター、およびドメイン コントローラー) に対する ACE が作成されます。
  
フォレストの準備とドメインの準備によって作成および追加されたパブリック Ace の詳細については、「 [skype For Business server でのフォレストの準備による変更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)」および展開ドキュメントの「 [Skype for business server でのドメインの準備](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md)によって行われる変更」を参照してください。
  
組織は、セキュリティリスクを軽減するために Active Directory ドメインサービス (AD DS) をロックダウンすることがよくあります。 ただし、ロックダウンされた Active Directory 環境では、Skype for Business Server で必要なアクセス許可を制限できます。 たとえば、コンテナーと OU からの ACE の削除や、ユーザー、連絡先、InetOrgPerson、コンピューターの各オブジェクトでのアクセス許可の継承の無効化などが挙げられます。 ロックダウンされた Active Directory 環境では、アクセス許可を必要とするコンテナーと Ou に対して手動でアクセス許可を設定する必要があります。
  
## <a name="server-information"></a>サーバー情報

アクティブ化の際に、Skype for Business Server は、次の3つの場所 (Active Directory ドメインサービス内) にサーバー情報を公開します。
  
- Skype for Business Server がインストールされている物理コンピューターに対応する各 Active Directory コンピューターオブジェクトのサービス接続ポイント (SCP)。
    
- **msRTCSIP-Pools** クラスのコンテナーに作成されるサーバー オブジェクト。
    
- トポロジビルダーで指定された信頼できるサーバー。
    
## <a name="service-connection-points"></a>サービス接続ポイント

Active Directory ドメインサービス内の各 Skype for Business Server オブジェクトには、RTC Services という SCP があります。これには、各コンピューターを識別し、提供するサービスを指定する多数の属性が含まれます。 さらに重要な SCP 属性には、 *serviceDNSName* 、 *serviceDNSNameType* 、 *serviceClassname* 、および*serviceBindingInformation*があります。 サードパーティの資産管理アプリケーションは、このような SCP の属性を照会することによって、展開を通じてサーバーの情報を取得できます。
  
## <a name="active-directory-server-objects"></a>Active Directory Server オブジェクト

各 Skype for Business Server の役割には、対応する Active Directory オブジェクトがあり、属性によって提供されるサービスがその役割によって定義されます。 また、Standard Edition サーバーがアクティブ化されたとき、または Enterprise Edition プールを作成したときに、Skype for Business Server によって**msrtcsip-userenabled true**コンテナーに新しい**msrtcsip-userenabled true**オブジェクトが作成されます。 **Msrtcsip-userenabled true**クラスは、プールの完全修飾ドメイン名 (FQDN) を、プールのフロントエンドコンポーネントとバックエンドコンポーネントの間の関連付けと共に指定します。 (Standard Edition サーバーは、フロントエンドとバックエンドが1台のコンピュータに併置されている論理プールと見なされます)。
  
## <a name="trusted-servers"></a>信頼済みのサーバー

Skype for Business Server では、[信頼済みサーバー] は、トポロジビルダーを実行してトポロジを公開するときに指定したものです。 公開したトポロジは、すべてのサーバー情報を含めて、中央管理ストアに格納されます。 中央管理ストアで定義されているサーバーのみが信頼されます。 Skype for Business Server では、信頼されているサーバーは次の条件を満たしています。
  
- サーバーの FQDN が、中央管理ストアに格納されているトポロジに出現する。
    
- サーバーが、信頼されている CA からの有効な証明書を提示している。 詳細については、「 [skype For Business server 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」または「 [Skype for business Server 2019 のシステム要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。
    
このどちらかの条件が満たされていない場合、サーバーは信頼されず、サーバーとの接続は拒否されます。 この double 要件により、不正なサーバーが有効なサーバーの FQDN を使用しようとしている攻撃を防ぐことができます。
  
さらに、Microsoft Office Communications Server 2007 R2 および Microsoft Office Communications Server 2007 の展開を有効にして、Skype for Business Server サーバーと通信するために、Skype for Business Server はフォレストの準備中にコンテナーを作成します。以前のリリースで信頼できるサーバーの一覧を保持する場合。 次の表は、以前の展開との互換性維持のために作成されるコンテナーを示しています。
  
**以前のリリースとの互換性を確保するために、信頼されたサーバーの一覧とその Active Directory コンテナー**

|**信頼済みのサーバーのリスト**|**Active Directory コンテナー**|
|:-----|:-----|
|Standard Edition サーバーおよびエンタープライズ プールのフロント エンド サーバー  <br/> |RTC サービス/グローバル設定  <br/> |
|会議サーバー  <br/> |RTC サービス/信頼済み MCU  <br/> |
|Web コンポーネント サーバー  <br/> |RTC サービス/TrustedWebComponentsServers  <br/> |
|仲介サーバーと Communicator Web Access サーバー、アプリケーション サーバー、レジストラーと QoE、音声ビデオ会議サービス (サードパーティの SIP サーバーを含む)  <br/> |RTC サービス/信頼済みサービス  <br/> |
|プロキシ サーバー  <br/> |Skype for Business Server がプロキシサーバーの下位互換性をサポートしていない  <br/> |
   

## <a name="see-also"></a>関連項目

[Skype for Business Server 用 Active Directory の準備](../../deploy/install/prepare-active-directory.md)
