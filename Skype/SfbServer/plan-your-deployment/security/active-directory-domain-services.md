---
title: Active Directory ドメイン サービス for Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory ドメイン サービスは、Windows Server 2003、Windows Server 2008、Windows Server 2012、および R2 ネットワークWindows Server 2012サービスとして機能します。 Active Directory ドメイン サービスは、セキュリティ インフラストラクチャを構築する基盤Skype for Business Server機能します。 このセクションの目的は、ユーザーが Active Directory ドメイン Skype for Business Serverを使用して IM、Web 会議、メディア、および音声の信頼できる環境を作成する方法を説明します。 Active Directory ドメイン サービス用の環境の準備の詳細については、「展開」のドキュメントSkype for Business Serverを参照してください。 Windows Server のネットワークにおける Active Directory ドメイン サービスの役割の詳細については、お使いのバージョンのオペレーティング システムのドキュメントを参照してください。
ms.openlocfilehash: 4af4e4b4dd7a64dd133d36a55ca1c334a12fe97e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604656"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Active Directory ドメイン サービス for Skype for Business Server
 
Active Directory ドメイン サービスは、Windows Server 2003、Windows Server 2008、Windows Server 2012、および R2 ネットワークWindows Server 2012サービスとして機能します。 Active Directory ドメイン サービスは、セキュリティ インフラストラクチャを構築する基盤Skype for Business Server機能します。 このセクションの目的は、ユーザーが Active Directory ドメイン Skype for Business Serverを使用して IM、Web 会議、メディア、および音声の信頼できる環境を作成する方法を説明します。 Active Directory ドメイン サービス用の環境の準備の詳細については、「展開」のドキュメント[Skype for Business Serverを参照](../../deploy/install/install.md)してください。 Windows Server のネットワークにおける Active Directory ドメイン サービスの役割の詳細については、お使いのバージョンのオペレーティング システムのドキュメントを参照してください。
  
Skype for Business Server Active Directory ドメイン サービスを使用して次の情報を保存します。
  
- フォレスト内で実行しているすべてのサーバー Skype for Business Serverグローバル設定が必要です。
    
- フォレスト内で実行しているすべてのサーバーの役割をSkype for Business Serverサービス情報。
    
- 一部のユーザー設定。
    
## <a name="active-directory-infrastructure"></a>Active Directory のインフラストラクチャ

Active Directory のインフラストラクチャ要件には、次のようなものがあります。
  
- ドメイン コントローラーのオペレーティング システム要件
    
- ドメインとフォレストの機能レベルの要件
    
- グローバル カタログ ドメインの要件
    
詳細については、「環境要件 for [Skype for Business Server 2015」](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)または「Server [requirements for Skype for Business Server 2019」を参照](../../../SfBServer2019/plan/system-requirements.md)してください。
  
## <a name="universal-groups"></a>ユニバーサル グループ

フォレストの準備中に、Skype for Business Serverグローバル設定とサービスにアクセスして管理するアクセス許可を持つ Active Directory ドメイン サービス内にさまざまなユニバーサル グループを作成します。 作成されるユニバーサル グループには、次のようなものがあります。
  
- **管理グループ**。 これらのグループは、ネットワークの基本的な管理者Skype for Business Serverします。 フォレストの準備中に、これらの管理者グループは、インフラストラクチャ Skype for Business Serverに追加されます。
    
- **サービス グループ**。 これらのグループは、ユーザーが提供するさまざまなサービスにアクセスするために必要なサービス Skype for Business Server。
    
- **インフラストラクチャ グループ**。 これらのグループは、特定のインフラストラクチャの特定の領域にアクセスSkype for Business Serverします。 変更したり、ユーザーを直接追加したりしないでください。 フォレストの準備中に、特定のサービスグループと管理グループが適切なインフラストラクチャ グループに追加されます。
    
AD for Skype for Business Server の準備時に作成される特定のユニバーサル グループ、およびインフラストラクチャ グループに追加されるサービスグループと管理グループの詳細については、「展開」のドキュメントの[「Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)のフォレスト準備による変更」を参照してください。
  
> [!NOTE]
> Skype for Business Serverは、ドメイン コントローラー用の Windows Server 2012サーバー 2003 オペレーティング システムWindowsユニバーサル グループをサポートします。 ユニバーサル グループのメンバーには、ドメイン ツリーまたはフォレスト内の任意のドメインの他のグループとアカウントを含め、ドメイン ツリーまたはフォレスト内の任意のドメインにアクセス許可を割り当てることができます。 ユニバーサル グループのサポートは、管理者の委任と組み合わせて、展開の管理をSkype for Business Serverします。 たとえば、管理者が両方を管理するには、あるドメインを別のドメインに追加する必要はありません。 
  
## <a name="role-based-access-control"></a>役割ベースのアクセス制御

ユニバーサル サービスグループと管理グループの作成、適切なユニバーサル グループへのサービスグループと管理グループの追加に加えて、フォレストの準備によって、Role-Basedアクセス制御 (RBAC) グループも作成されます。 フォレストの準備によって作成された特定の RBAC グループの詳細については、「展開」のドキュメントの「Skype for Business Serverフォレストの準備[による](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)変更」を参照してください。 RBAC グループの詳細については、「役割ベースのアクセス制御[(RBAC) for Skype for Business Server」 を参照してください](role-based-access-control-rbac.md)。
  
## <a name="access-control-entries-aces-and-inheritance"></a>アクセス制御エントリ (ACE) と継承

フォレストの準備では、プライベート ACE とパブリック ACE の両方が作成され、ユニバーサル グループの ACE が追加されます。 ユーザーが使用するグローバル設定コンテナーに特定のプライベート Skype for Business Server。 このコンテナーは Skype for Business Server でのみ使用され、グローバル設定の保存場所に応じて、ルート ドメインの構成コンテナーまたは System コンテナーに格納されます。
  
ドメインの準備ステップでは、ドメイン内のユーザーをホストおよび管理するアクセス許可を与えるアクセス制御エントリ (ACE) をユニバーサル グループに追加します。ドメインの準備で、ドメイン ルートと 3 つの組み込みコンテナー (ユーザー、コンピューター、およびドメイン コントローラー) に対する ACE が作成されます。
  
フォレストの準備とドメイン準備によって作成および追加されたパブリック[ACEs](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md)の詳細については、「展開」のドキュメントの「Skype for Business Server でのフォレストの準備による変更」と[「Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)のドメイン準備による変更」を参照してください。
  
組織では、セキュリティ リスクを軽減するために Active Directory ドメイン サービス (AD DS) をロックダウンすることがよくあります。 ただし、ロックダウンされた Active Directory 環境では、必要なアクセス許可Skype for Business Serverがあります。 たとえば、コンテナーと OU からの ACE の削除や、ユーザー、連絡先、InetOrgPerson、コンピューターの各オブジェクトでのアクセス許可の継承の無効化などが挙げられます。 ロックダウンされた Active Directory 環境では、コンテナーと OU のアクセス許可を必要に応じて手動で設定する必要があります。
  
## <a name="server-information"></a>サーバー情報

ライセンス認証中、Skype for Business Server Active Directory ドメイン サービスの次の 3 つの場所にサーバー情報を発行します。
  
- インストールされている物理コンピューターに対応する各 Active Directory コンピューター オブジェクトのサービス接続ポイント (SCP) Skype for Business Serverします。
    
- **msRTCSIP-Pools** クラスのコンテナーに作成されるサーバー オブジェクト。
    
- トポロジ ビルダーで指定された信頼済みサーバー。
    
## <a name="service-connection-points"></a>サービス接続ポイント

Active Directory ドメイン Skype for Business Serverの各オブジェクトには、RTC Services と呼ばれる SCP が含まれています。このオブジェクトには、各コンピューターを識別し、提供するサービスを指定する属性が多数含まれています。 より重要な SCP 属性の中には *、serviceDNSName、serviceDNSNameType、serviceClassname、serviceBindingInformation* *があります*。   サード パーティ製のアセット管理アプリケーションは、これらの属性や他の SCP 属性に対してクエリを実行することで、展開全体でサーバー情報を取得できます。
  
## <a name="active-directory-server-objects"></a>Active Directory サーバー オブジェクト

各Skype for Business Serverサーバー ロールには、対応する Active Directory オブジェクトが含まれます。その属性は、その役割によって提供されるサービスを定義します。 また、Standard Edition サーバーがアクティブ化されている場合、または Enterprise Edition プールが作成されると、Skype for Business Server は **msRTCSIP-Pool** コンテナーに新しい **msRTCSIP-Pool** オブジェクトを作成します。 **msRTCSIP-Pool** クラスは、プールの完全修飾ドメイン名 (FQDN) と、プールのフロントエンド コンポーネントとバック エンド コンポーネントの関連付けを指定します。 (Standard Editionサーバーは論理プールと見なされ、フロント エンドとバック エンドは 1 台のコンピューターに接続されます)。
  
## <a name="trusted-servers"></a>信頼済みのサーバー

このSkype for Business Serverは、トポロジ ビルダーを実行してトポロジを発行するときに指定されたサーバーです。 公開したトポロジは、すべてのサーバー情報を含めて、中央管理ストアに格納されます。 中央管理ストアで定義されているサーバーのみが信頼されます。 このSkype for Business Server信頼できるサーバーは、次の条件を満たすサーバーです。
  
- サーバーの FQDN が、中央管理ストアに格納されているトポロジに出現する。
    
- サーバーが、信頼されている CA からの有効な証明書を提示している。 詳細については、「環境要件 for [Skype for Business Server 2015」](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)または「System requirements for Skype for Business Server [2019」を参照](../../../SfBServer2019/plan/system-requirements.md)してください。
    
このどちらかの条件が満たされていない場合、サーバーは信頼されず、サーバーとの接続は拒否されます。 この二重要件により、不正なサーバーが有効なサーバーの FQDN を引き継ぐ可能性が低い場合に攻撃を防ぐ。
  
さらに、Microsoft Office Communications Server 2007 R2 および Microsoft Office Communications Server 2007 展開を有効にして Skype for Business Server サーバーと通信するために、Skype for Business Server は以前のリリースの信頼済みサーバーのリストを保持するためのフォレストの準備中にコンテナーを作成します。 次の表は、以前の展開との互換性維持のために作成されるコンテナーを示しています。
  
**信頼済みのサーバーのリストと、以前のリリースとの互換性を維持するための Active Directory コンテナー**

|**信頼済みのサーバーのリスト**|**Active Directory コンテナー**|
|:-----|:-----|
|Standard Edition サーバーおよびエンタープライズ プールのフロント エンド サーバー  <br/> |RTC サービス/グローバル設定  <br/> |
|会議サーバー  <br/> |RTC サービス/信頼済み MCU  <br/> |
|Web コンポーネント サーバー  <br/> |RTC サービス/TrustedWebComponentsServers  <br/> |
|仲介サーバーと Communicator Web Access サーバー、アプリケーション サーバー、レジストラーと QoE、音声ビデオ会議サービス (サードパーティの SIP サーバーを含む)  <br/> |RTC サービス/信頼済みサービス  <br/> |
|プロキシ サーバー  <br/> |Skype for Business Serverサーバーの下位互換性はサポートされていません  <br/> |
   

## <a name="see-also"></a>関連項目

[Active Directory for Skype for Business Server](../../deploy/install/prepare-active-directory.md)
