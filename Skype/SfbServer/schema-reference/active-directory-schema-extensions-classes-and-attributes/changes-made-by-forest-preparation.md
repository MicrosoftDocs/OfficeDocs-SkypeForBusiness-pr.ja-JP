---
title: Skype でビジネス サーバーは、フォレストの準備によって加えられた変更
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: このセクションでは、グローバル設定とオブジェクト、およびフォレストの準備手順で作成されたユニバーサル サービスと管理グループについて説明します。
ms.openlocfilehash: 3e37948cae33412ac028d5190c780d6bee5aeeb2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Skype でビジネス サーバーは、フォレストの準備によって加えられた変更
 
このセクションでは、グローバル設定とオブジェクト、およびフォレストの準備手順で作成されたユニバーサル サービスと管理グループについて説明します。
  
## <a name="active-directory-global-settings-and-objects"></a>Active Directory のグローバル設定とオブジェクト

場合 (同様にビジネスのサーバーの展開のすべての新しい Skype の)、構成コンテナーにグローバル設定を保存すると、フォレストの準備が既存のサービス コンテナーを使用し、Configuration\Services の下にある**RTC サービス**オブジェクトを追加オブジェクトです。 RTC サービス オブジェクトの下は、フォレストの準備は、型 msRTCSIP ・ GlobalContainer の**グローバル設定**オブジェクトを追加します。 グローバル設定オブジェクトは、ビジネスのサーバーの展開の Skype に適用されるすべての設定を保持します。 システム コンテナーにグローバル設定を保存する場合、フォレストの準備は、ルート ドメイン システム コンテナーの下の Microsoft コンテナーと System\Microsoft オブジェクトの下にある RTC サービス オブジェクトを使用します。
  
フォレストの準備は、プロシージャが実行されるルート ドメインの新しい**ドメインを msRTCSIP**オブジェクトにも追加されます。
  
## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory ユニバーサル サービスと管理グループ

フォレストの準備では、指定したドメインを基にユニバーサル グループを作成し、これらのグループのアクセス制御エントリ (Ace) を追加します。 この手順では、指定したドメインのユーザー コンテナーにユニバーサル グループを作成します。 
  
ユニバーサル グループには、アクセスし、グローバル設定とサービスを管理する管理者が使用できます。 フォレストの準備は、次の種類のユニバーサル グループを追加します。
  
- **管理グループ**これらのグループは、ビジネス サーバー ネットワークでの Skype の管理者の役割を定義します。
    
- **インフラストラクチャ ・ グループ**これらのグループは、ビジネスのサーバー インフラストラクチャの Skype の特定の領域にアクセスするアクセス許可を提供します。 管理グループの構成要素として機能します。 これらのグループを変更しなかったり、それらに直接ユーザーを追加する必要があります。
    
- **サービス グループ**これらのグループは、ビジネス サービスのさまざまな Skype にアクセスするために必要なサービス アカウントです。
    
次の表では、管理グループについて説明します。
  
**フォレストの準備時に作成された管理グループ**

|**管理グループ**|**説明**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |サーバーとすべてのサーバー ロールを含む、プールの設定、グローバル設定、およびユーザーを管理するためにメンバーを使用できます。  <br/> |
|RTCUniversalUserAdmins  <br/> |ユーザー設定を管理し、1 つのサーバーまたはプールからユーザーを移動するメンバーを使用できます。  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |メンバー サーバー、プール、およびユーザーの設定を読み取ることができます。  <br/> |
   
次の表では、インフラストラクチャ グループについて説明します。
  
**フォレストの準備時に作成されるインフラストラクチャ グループ**

|**インフラストラクチャ グループ**|**説明**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Skype のビジネスのサーバーのグローバル設定オブジェクトに対する書き込みアクセス権を付与します。  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Skype のビジネスのサーバーのグローバル設定オブジェクトへの読み取り専用アクセスを付与します。  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Skype をビジネスのサーバーのユーザー設定の読み取り専用アクセスを付与します。  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Skype をビジネスのサーバー設定の読み取り専用アクセスを付与します。 このグループには、プール レベルの設定、個々 のサーバーに固有の設定にのみへのアクセス権がありません。  <br/> |
|RTCUniversalSBATechnicians  <br/> |Skype をビジネスのサーバー構成の読み取り専用アクセスを付与し、インストール時に、リカバリ性に優れたブランチ アプライアンスのローカル管理者グループに配置されます。  <br/> |
   
次の表では、サービス グループについて説明します。
  
**フォレストの準備時に作成されるサービス グループ**

|**サービス グループ**|**説明**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |フロント エンド サーバーと Standard Edition サーバーの実行に使用されるサービス アカウントが含まれています。 このグループでは、ビジネスのサーバーのグローバル設定および Active Directory ユーザー オブジェクトの Skype にサーバーの読み取り/書き込みアクセスを許可します。  <br/> |
|RTCComponentUniversalServices  <br/> |A を実行するために使用するサービス アカウントが含まれています/V 会議サーバー、Web サービス、仲介サーバー、アーカイブ サーバー、およびサーバーを監視します。  <br/> |
|RTCProxyUniversalServices  <br/> |Skype をビジネス サーバーのエッジ サーバーの実行に使用されるサービス アカウントが含まれています。  <br/> |
|RTCUniversalConfigReplicator  <br/> |ビジネス サーバーの中央管理ストアのレプリケーションの Skype にはサポートしているサーバーが含まれます。  <br/> |
|RTCSBAUniversalServices  <br/> |Skype をビジネスのサーバー設定の場合は、読み取り専用アクセスを付与しますが、リカバリ性に優れたブランチ サーバーとブランチのリカバリ性に優れた機器の配置のインストールの構成では。  <br/> |
   
フォレストの準備をしは、次のように、適切なインフラストラクチャ グループにサービスと管理グループを追加します。
  
- RTCUniversalServerAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup に追加されます。
    
- RTCUniversalUserAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加されます。
    
- RTCHSUniversalServices、RTCComponentUniversalServices および RTCUniversalReadOnlyAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、RTCUniversalUserReadOnlyGroup のメンバーとして追加されます。
    
フォレストの準備には、次の役割に基づくアクセス制御 (RBAC) グループも作成されます。
  
- CSAdministrator
    
- CSArchivingAdministrator
    
- CSHelpDesk
    
- CSLocationAdministrator
    
- CSResponseGroupAdministrator
    
- CSServerAdministrator
    
- CSUserAdministrator
    
- CSViewOnlyAdministrator
    
- CSVoiceAdministrator
    
- CsPersistentChatAdministator
    
- CsResponseGroupManager
    
RBAC の役割と、それぞれのタスクについての詳細は、計画のドキュメントで[の役割ベースのアクセス制御](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)を参照してください。
  
フォレストの準備では、プライベートとパブリックの両方の Ace を作成します。 Skype によってビジネスのサーバーが使用するグローバル設定コンテナーに秘密の Ace が作成されます。 このコンテナーでは、ビジネスのサーバーの Skype によってのみ使用され、構成コンテナーまたはグローバル設定を保存する場所によって、ルート ドメインのシステム コンテナーであります。 フォレストの準備によって作成されたパブリック Ace は、次の表に表示されます。
  
**フォレストの準備によって作成するパブリック Ace**

|**ACE**|**RTCUniversalGlobalReadOnlyGroup**|
|:-----|:-----|
|ルート ドメイン システム コンテナーが (継承なし) を読む**\*** <br/> |X  <br/> |
|構成の読み込みの DisplaySpecifiers のコンテナー (継承なし)  <br/> |X  <br/> |
   
> [!NOTE]
> **\***継承されない Ace では、これらのコンテナーの下の子オブジェクトへのアクセスは付与しません。 継承された Ace では、これらのコンテナーの下にある子オブジェクトへのアクセスを許可します。 
  
構成名前付けコンテキストの下で、構成コンテナーには、フォレストの準備は、次のタスクを実行します。
  
- **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** **、RTC プロパティ**ページの adminContextMenu の下にエントリを追加し、ユーザー、連絡先、および Inetorgperson の指定子を表示する言語の adminPropertyPages の属性 (たとえば、CN =ユーザーの表示、CN = 409、CN = DisplaySpecifiers)。
    
- ユーザーおよび連絡先のクラスに適用される**権限の拡張**では、型**controlAccessRight**の**RTCPropertySet**オブジェクトを追加します。
    
- [ユーザー、連絡先、OU、および DomainDNS クラスに適用される**権限の拡張**型**controlAccessRight**の**RTCUserSearchPropertySet**オブジェクトを追加します。
    
- 各言語の組織単位 (OU) の表示指定子の**extraColumns**属性] の下の**msRTCSIP PrimaryUserAddress**を追加する (たとえば、CN = 組織単位の表示、CN = 409、CN = DisplaySpecifiers) の値をコピーし、既定の表示の**extraColumns**属性 (たとえば、CN = の既定の表示、CN = 409、CN = DisplaySpecifiers)。
    
- **MsRTCSIP PrimaryUserAddress**、 **msRTCSIP PrimaryHomeServer**、および**msRTCSIP UserEnabled**の各言語の**attributeDisplayNames**属性の下の属性をフィルター処理は、ユーザー、連絡先、指定子を表示を追加します。および InetOrgPerson オブジェクト (たとえば、英語で: CN = ユーザーの表示、CN = 409、CN = DisplaySpecifiers)。
    

