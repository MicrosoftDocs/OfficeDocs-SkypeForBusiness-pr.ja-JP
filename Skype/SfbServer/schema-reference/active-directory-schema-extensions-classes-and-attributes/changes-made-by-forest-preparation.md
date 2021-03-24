---
title: Skype for Business Server でのフォレストの準備によって行われた変更
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: ここでは、グローバル設定とオブジェクト、およびフォレストの準備中に作成するユニバーサル サービス グループとユニバーサル管理グループについて説明します。
ms.openlocfilehash: b304dbb12cb7e05e7bc82bdc56ffc330ce0221c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098653"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Skype for Business Server でのフォレストの準備によって行われた変更

ここでは、グローバル設定とオブジェクト、およびフォレストの準備中に作成するユニバーサル サービス グループとユニバーサル管理グループについて説明します。

## <a name="active-directory-global-settings-and-objects"></a>Active Directory のグローバル設定とオブジェクト

構成コンテナーにグローバル設定を格納する場合 (すべての新しい Skype for Business Server 展開の場合と同様)、フォレストの準備では既存のサービス コンテナーを使用し、Configuration\Services オブジェクトの下に **RTC Service** オブジェクトを追加します。 フォレストの準備では、msRTCSIP-GlobalContainer 型の **Global Settings** オブジェクトが RTC サービス オブジェクトに追加されます。 グローバル設定オブジェクトには、Skype for Business Server 展開に適用される設定すべてが保持されます。 グローバル設定をシステム コンテナーに保存する場合は、フォレストの準備で新しい ルート ドメインのシステム コンテナーの下の Microsoft コンテナーと、システム\Microsoft オブジェクトの下の RTC サービス オブジェクトが使用されます。

またフォレストの準備では、この手順が実行されるルート ドメインの新しい **msRTCSIP-Domain** オブジェクトが追加されます。

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory のユニバーサル サービス グループとユニバーサル管理グループ

フォレストの準備では、指定したドメインを基にユニバーサル グループを作成し、これらのグループのアクセス制御エントリ (ACE) を追加します。このステップにより、指定したドメインのユーザー コンテナーにユニバーサル グループが作成されます。

ユニバーサル グループを使用すると、管理者はグローバル設定およびサービスにアクセスしてそれらを管理できます。フォレストの準備により、次の種類のユニバーサル グループが追加されます。

- **管理グループ** これらのグループは、Skype for Business Server ネットワークの管理者の役割を定義します。

- **インフラストラクチャ グループ** これらのグループは、Skype for Business Server インフラストラクチャの特定の領域にアクセスするためのアクセス許可を提供します。 管理グループのコンポーネントとして機能します。 これらのグループを変更したり、ユーザーを直接追加したりすることはできません。

- **サービス グループ** これらのグループは、さまざまな Skype for Business Server サービスにアクセスするために必要なサービス アカウントです。

次の表では、管理グループについて説明します。

**フォレストの準備時に作成される管理グループ**

|**管理グループ**|**説明**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |このグループのメンバーは、すべてのサーバーの役割、グローバル設定、ユーザーなど、サーバーおよびプールの設定を管理できます。  <br/> |
|RTCUniversalUserAdmins  <br/> |このグループのメンバーは、ユーザー設定を管理したり、あるサーバーまたはプールから、別のサーバーまたはプールにユーザーを移動したりできます。  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |このグループのメンバーは、サーバー、プール、およびユーザーの設定を読み取ることができます。  <br/> |

次の表では、インフラストラクチャ グループについて説明します。

**フォレストの準備時に作成されるインフラストラクチャ グループ**

|**インフラストラクチャ グループ**|**説明**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Skype for Business Server のグローバル設定オブジェクトへの書き込みアクセスを許可します。  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Skype for Business Server のグローバル設定オブジェクトへの読み取り専用アクセス権を付与します。  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Skype for Business Server ユーザー設定への読み取り専用アクセス権を付与します。  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Skype for Business Server 設定への読み取り専用アクセス権を付与します。 このグループは、プール レベルの設定にはアクセスできず、個々のサーバーに固有の設定のみにアクセスできます。  <br/> |
|RTCUniversalSBATechnicians  <br/> |Skype for Business Server 構成への読み取り専用アクセスを許可し、インストール中に存続可能ブランチ アプライアンスのローカル管理者グループに配置されます。  <br/> |

次の表では、サービス グループについて説明します。

**フォレストの準備時に作成されるサービス グループ**

|**サービス グループ**|**説明**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |フロントエンド サーバーと Standard Edition サーバーの実行に使用されるサービス アカウントが含まれます。 このグループでは、サーバーは Skype for Business Server のグローバル設定と Active Directory ユーザー オブジェクトへの読み取り/書き込みアクセスを許可します。  <br/> |
|RTCComponentUniversalServices  <br/> |音声ビデオ会議サーバー、Web サービス、仲介サーバー、アーカイブ サーバー、監視サーバーの実行に使用されるサービス アカウントが含まれます。  <br/> |
|RTCProxyUniversalServices  <br/> |Skype for Business Server エッジ サーバーの実行に使用されるサービス アカウントが含まれます。  <br/> |
|RTCUniversalConfigReplicator  <br/> |Skype for Business Server Central Management ストアレプリケーションに参加できるサーバーが含まれます。  <br/> |
|RTCSBAUniversalServices  <br/> |Skype for Business Server 設定への読み取り専用アクセスを許可しますが、存続可能ブランチ サーバーと存続可能ブランチ アプライアンス展開のインストールの構成を許可します。  <br/> |

フォレストの準備では、次に示すサービス グループと管理グループをインフラストラクチャ グループに追加します。

- RTCUniversalServerAdmins を、RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup に追加します。

- RTCUniversalUserAdmins を、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加します。

- RTCHSUniversalServices、RTCComponentUniversalServices、および RTCUniversalReadOnlyAdmins を、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加します。

フォレストの準備によって、次の役割ベースのアクセス制御 (RBAC) グループも作成されます。

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

RBAC の役割、および各役割で許可されるタスクの詳細については、「計画」のドキュメントの「[Role-Based Access Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)」を参照してください。

フォレストの準備では、プライベート ACE とパブリック ACE の両方を作成します。 Skype for Business Server で使用されるグローバル設定コンテナーにプライベート ACEs を作成します。 このコンテナーは Skype for Business Server でのみ使用され、グローバル設定の保存場所に応じて、構成コンテナーまたはルート ドメインの System コンテナーに格納されます。 フォレストの準備で作成するパブリック ACE の一覧を次の表に示します。

**フォレストの準備で作成するパブリック ACE**


| **ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| ルート ドメインのシステム コンテナーの読み取り (継承されません) **\\**\* <br/>        | ○  <br/>                            |
| 構成の DisplaySpecifiers コンテナーの読み取り (継承されません)  <br/> | ○  <br/>                            |

> [!NOTE]
> <strong>\\</strong>継承されない *ACEs は、これらのコンテナーの下の子オブジェクトへのアクセスを許可しません。 継承された ACEs は、これらのコンテナーの下の子オブジェクトへのアクセスを許可します。

フォレストの準備では、構成名前付けコンテキストの下の構成コンテナーで次のタスクを実行します。

- **RTC property** ページのエントリ **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** を、ユーザー、連絡先、および InetOrgPersons の言語表示指定子の adminContextMenu および adminPropertyPages 属性に追加します (CN=user-Display、CN=409、CN=DisplaySpecifiers など)。

- User クラスと Contact クラスに適用される **Extended-Rights** に、**controlAccessRight** 型の **RTCPropertySet** オブジェクトを追加します。

- User、Contact、OU、および DomainDNS クラスに適用される **Extended-Rights** に、**controlAccessRight** 型の **RTCUserSearchPropertySet** オブジェクトを追加します。

- 各言語の組織単位 (OU) の表示指定子の **extraColumns** 属性に **msRTCSIP-PrimaryUserAddress** を追加し (CN=organizationalUnit-Display、CN=409、CN=DisplaySpecifiers など)、既定の表示の **extraColumns** 属性の値をコピーします (CN=default-Display、CN=409、CN=DisplaySpecifiers など)。

- **msRTCSIP-PrimaryUserAddress**、**msRTCSIP-PrimaryHomeServer**、および **msRTCSIP-UserEnabled** フィルター属性を、Users、Contacts、および InetOrgPerson オブジェクトの各言語表示指定子の **attributeDisplayNames** 属性に追加します (たとえば英語では、CN=user-Display、CN=409、CN=DisplaySpecifiers など)。