---
title: Skype for Business Server でのフォレストの準備によって行われた変更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: このセクションでは、グローバル設定とオブジェクト、およびフォレストの準備手順によって作成されるユニバーサルサービスと管理グループについて説明します。
ms.openlocfilehash: 26917915d89aff721e74f094eb8ad5bb72db3cf6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815535"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Skype for Business Server でのフォレストの準備によって行われた変更

このセクションでは、グローバル設定とオブジェクト、およびフォレストの準備手順によって作成されるユニバーサルサービスと管理グループについて説明します。

## <a name="active-directory-global-settings-and-objects"></a>Active Directory のグローバル設定とオブジェクト

構成コンテナーにグローバル設定を格納する場合 (すべての新しい Skype for Business Server の展開の場合と同様)、フォレストの準備では既存のサービスコンテナーが使用され、Configuration\Services オブジェクトの下に**RTC サービス**オブジェクトが追加されます。 RTC Service オブジェクトの下で、フォレストの準備によって型が Msrtcsip-userenabled true-GlobalContainer の**グローバル設定**オブジェクトが追加されます。 グローバル設定オブジェクトには、Skype for Business Server の展開に適用されるすべての設定が含まれます。 システムコンテナーにグローバル設定を保存する場合、フォレストの準備では、ルートドメインシステムコンテナーと、System\Microsoft オブジェクトの下にある RTC サービスオブジェクトを使って Microsoft コンテナーを使用します。

フォレストの準備では、この手順を実行するルートドメイン用の新しい**msrtcsip-userenabled true**オブジェクトも追加されます。

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory ユニバーサルサービスと管理グループ

フォレストの準備によって、指定したドメインに基づいてユニバーサルグループが作成され、これらのグループにアクセス制御エントリ (Ace) が追加されます。 この手順では、指定したドメインのユーザーコンテナーでユニバーサルグループを作成します。

ユニバーサルグループを使用すると、管理者はグローバル設定とサービスにアクセスして管理することができます。 フォレストの準備によって、次の種類のユニバーサルグループが追加されます。

- **管理グループ**これらのグループは、Skype for Business Server ネットワークの管理者ロールを定義します。

- **インフラストラクチャグループ**これらのグループは、Skype for Business Server インフラストラクチャの特定の領域にアクセスするためのアクセス許可を提供します。 これらは、管理グループのコンポーネントとして機能します。 これらのグループを変更したり、これらのグループにユーザーを直接追加したりすることはできません。

- **サービスグループ**これらのグループは、さまざまな Skype for Business Server サービスへのアクセスに必要なサービスアカウントです。

次の表では、管理グループについて説明します。

**フォレストの準備中に作成された管理グループ**

|**管理グループ**|**説明**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |すべてのサーバーの役割、グローバル設定、ユーザーなど、サーバーとプールの設定を管理することをメンバーに許可します。  <br/> |
|RTCUniversalUserAdmins  <br/> |メンバーがユーザー設定を管理し、あるサーバーまたはプール間でユーザーを移動できるようにします。  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |サーバー、プール、ユーザー設定の読み取りをメンバーに許可します。  <br/> |

次の表では、インフラストラクチャグループについて説明します。

**フォレストの準備中に作成されたインフラストラクチャグループ**

|**インフラストラクチャグループ**|**説明**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Skype for Business Server のグローバル設定オブジェクトへの書き込みアクセス権を付与します。  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Skype for Business Server のグローバル設定オブジェクトへの読み取り専用アクセスを許可します。  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Skype for Business Server のユーザー設定への読み取り専用アクセス権を付与します。  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Skype for Business Server の設定への読み取り専用アクセス権を付与します。 このグループは、個々のサーバーに固有の設定のみに、プールレベルの設定にアクセスすることはできません。  <br/> |
|RTCUniversalSBATechnicians  <br/> |Skype for Business Server の設定への読み取り専用アクセス権を付与し、インストール中に survivable branch アプライアンスのローカル管理者グループに配置されます。  <br/> |

次の表では、サービスグループについて説明します。

**フォレストの準備中に作成されたサービスグループ**

|**サービスグループ**|**説明**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |フロントエンドサーバーおよび Standard Edition サーバーの実行に使用するサービスアカウントが含まれています。 このグループでは、Skype for Business Server のグローバル設定と Active Directory ユーザーオブジェクトへのサーバーの読み取り/書き込みアクセスが許可されています。  <br/> |
|RTCComponentUniversalServices  <br/> |A/V 会議サーバー、Web サービス、仲介サーバー、アーカイブサーバー、監視サーバーの実行に使用されるサービスアカウントが含まれています。  <br/> |
|RTCProxyUniversalServices  <br/> |Skype for Business Server Edge サーバーを実行するために使用されるサービスアカウントが含まれています。  <br/> |
|RTCUniversalConfigReplicator  <br/> |Skype for Business Server 全体管理ストアのレプリケーションに参加できるサーバーが含まれています。  <br/> |
|RTCSBAUniversalServices  <br/> |Skype for Business Server の設定への読み取り専用アクセス権を付与しますが、survivable branch server と survivable branch appliance の展開をインストールするための構成を許可します。  <br/> |

次に示すように、フォレストの準備によって、適切なインフラストラクチャグループにサービスグループと管理グループが追加されます。

- RTCUniversalServerAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup に追加されます。

- RTCUniversalUserAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加されます。

- RTCHSUniversalServices、RTCComponentUniversalServices、RTCUniversalReadOnlyAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加されます。

フォレストの準備では、次の役割ベースのアクセス制御 (RBAC) グループも作成されます。

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

RBAC の役割と、それぞれに対して許可されるタスクについて詳しくは、「計画ドキュメントの[役割ベースのアクセス制御](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)」をご覧ください。

フォレストの準備では、プライベート Ace とパブリック Ace の両方が作成されます。 Skype for Business Server で使用されるグローバル設定コンテナーにプライベート Ace を作成します。 このコンテナーは、Skype for Business Server でのみ使用され、グローバル設定を保存する場所に応じて、構成コンテナーまたはルートドメイン内のシステムコンテナーにあります。 次の表に、フォレストの準備によって作成されたパブリック Ace を示します。

**フォレストの準備によって作成されたパブリック Ace**


| **AS**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| ルートドメインシステムコンテナーを読み取ります (継承されません)**\\**\* <br/>        | X  <br/>                            |
| 構成の DisplaySpecifiers 子コンテナーを読み取ります (継承されません)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>* 継承されない Ace は、これらのコンテナーの下にある子オブジェクトへのアクセス権を付与しません。 継承された Ace は、これらのコンテナーの下にある子オブジェクトへのアクセス権を付与します。

構成コンテナーでは、構成の名前付けコンテキストの下で、フォレストの準備で次のタスクを実行します。

- ユーザー、連絡先、InetOrgPersons の言語表示指定子 (例: CN = ユーザー表示、CN = 409、CN = DisplaySpecifiers 子) の adminContextMenu**プロパティ**と adminPropertyPages 属性のエントリ **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** を追加します。

- ユーザークラスと連絡先クラスに適用される**拡張権限**の下に、 **controlaccessright**型の**RTCPropertySet**オブジェクトを追加します。

- ユーザー、連絡先、OU、および DomainDNS クラスに適用される**拡張権限**の下に、 **controlaccessright**型の**RTCUserSearchPropertySet**オブジェクトを追加します。

- 各言語の組織単位 (OU) 表示指定子の**extraColumns**属性の下に**Msrtcsip-userenabled true-primaryuseraddress**を追加します (例: Cn = organizationalUnit-display、CN = 409、cn = displayspecifiers 子)。既定の表示の**extraColumns**属性の値をコピーします (例: CN = default-DISPLAY、Cn = 409、cn = displayspecifiers 子)。

- ユーザー、連絡先、および InetOrgPerson オブジェクトの各言語表示指定子の**Attributedisplaynames**属性の**Msrtcsip-userenabled true-primaryuseraddress**、 **Msrtcsip-userenabled true-PrimaryHomeServer**、および**msrtcsip-userenabled true-userenabled**フィルター属性を追加します (たとえば、英語: CN = ユーザー表示、cn = 409、cn = display指定子)。


