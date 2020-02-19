---
title: 'Lync Server 2013: Lync Server の Active Directory ドメインサービス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f05832a3390101aad7acb1c9d25f532288ca020a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a>Lync Server 2013 の Active Directory ドメインサービス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-13_

Active Directory ドメインサービスは、Windows Server 2003、Windows Server 2008、Windows Server 2012、および Windows Server 2012 R2 ネットワークのディレクトリサービスとして機能します。 Active Directory ドメインサービスは、Microsoft Lync Server 2013 セキュリティインフラストラクチャを構築する基礎としても機能します。 このセクションの目的は、Lync Server 2013 が Active Directory ドメインサービスを使用して IM、Web 会議、メディア、および音声の信頼できる環境を作成する方法について説明することです。 Active Directory ドメインサービスに対する Lync Server extensions の詳細、および Active Directory ドメインサービス用の環境の準備については、「展開」のドキュメントの「 [Active Directory ドメインサービスの Lync server 2013 の準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。 Windows Server のネットワークにおける Active Directory ドメイン サービスの役割の詳細については、お使いのバージョンのオペレーティング システムのドキュメントを参照してください。

Lync Server 2013 は、Active Directory ドメインサービスを使用して次のものを格納します。

  - フォレスト内の Lync Server 2013 を実行しているすべてのサーバーに必要なグローバル設定。

  - フォレスト内の Lync Server 2013 を実行しているすべてのサーバーの役割を識別するサービス情報。

  - 一部のユーザー設定。

<div>

## <a name="active-directory-infrastructure"></a>Active Directory のインフラストラクチャ

Active Directory のインフラストラクチャ要件には、次のようなものがあります。

  - ドメイン コントローラーのオペレーティング システム要件

  - ドメインとフォレストの機能レベルの要件

  - グローバル カタログ ドメインの要件

詳細については、「展開」のドキュメントの「 [Lync Server 2013 の Active Directory インフラストラクチャ要件](lync-server-2013-active-directory-infrastructure-requirements.md)」を参照してください。

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Active Directory ドメイン サービスの準備

<div>


> [!NOTE]  
> グローバル設定はシステム コンテナーではなく構成コンテナーに展開することをお勧めします。 これによってセキュリティが向上するわけではありませんが、一部の Active Directory ドメイン サービスのトポロジではスケーラビリティが向上することがあります。 Microsoft Office Communications Server 2007 から移行していて、システムコンテナーを使用していて、構成コンテナーの使用を計画している場合は、アップグレードの準備を行う前に、システムコンテナーで設定を移動する必要があります。 システムコンテナー設定を構成コンテナーに移行するには、「Office Communications Server 2007 グローバル設定移行ツール<A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A>」を参照してください。



</div>

Lync Server 2013 を展開する場合、最初の手順として、Active Directory ドメインサービスを準備します。 Lync Server 2013 用の Active Directory ドメインサービスの準備は、次の3つの手順で構成されます。

  - **スキーマを準備**します。 このタスクは、Active Directory ドメインサービスのスキーマを拡張して、Lync Server 2013 に固有のクラスと属性を含めます。 スキーマの準備の詳細については、「展開」のドキュメントの「 [Lync Server 2013 での Active Directory スキーマの準備の実行](lync-server-2013-running-schema-preparation.md)」を参照してください。 詳細については、「 [Office Communications server 2007 R2 から Lync Server 2013 への移行](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)」を参照してください。

  - **フォレストを準備**します。 このタスクは、フォレストのルートドメインにグローバル設定とオブジェクトを作成し、これらの設定およびオブジェクトへのアクセスを管理するユニバーサルサービスおよび管理グループと共に作成します。 フォレストの準備の詳細については、「展開」のドキュメントの「 [Lync Server 2013 の実行フォレストの準備](lync-server-2013-running-forest-preparation.md)」を参照してください。

  - **ドメインを準備**します。 このタスクは、ドメイン内のユーザーをホストおよび管理するためのアクセス許可を付与するユニバーサルグループに必要なアクセス制御エントリ (Ace) を追加します。 このタスクは、Lync Server 2013 を実行しているサーバーを展開するすべてのドメインで、および Lync Server ユーザーが存在するすべてのドメインで完了する必要があります。 ドメインの準備の詳細については、「展開」のドキュメントの「 [Lync Server 2013 の実行ドメインの準備](lync-server-2013-running-domain-preparation.md)」を参照してください。

Active Directory を準備するための完全なプロセス、および各手順を実行するために必要な権限とアクセス許可の概要については、「展開」のドキュメントの「 [Lync Server 2013 の Active directory インフラストラクチャ要件](lync-server-2013-active-directory-infrastructure-requirements.md)」を参照してください。

</div>

<div>

## <a name="universal-groups"></a>ユニバーサル グループ

フォレストの準備時に、Lync Server 2013 は、グローバル設定とサービスにアクセスして管理するためのアクセス許可を持つ Active Directory ドメインサービス内にさまざまなユニバーサルグループを作成します。 作成されるユニバーサル グループには、次のようなものがあります。

  - **管理グループ**。 これらのグループは、Lync Server ネットワークの基本的な管理者の役割を定義します。 フォレストの準備中に、これらの管理者グループが Lync Server インフラストラクチャグループに追加されます。

  - **サービスグループ**。 これらのグループは、Lync Server で提供されるさまざまなサービスにアクセスするために必要なサービスアカウントです。

  - **インフラストラクチャグループ**。 これらのグループは、Lync Server インフラストラクチャの特定の領域にアクセスするためのアクセス許可を提供します。 変更したり、ユーザーを直接追加したりしないでください。 フォレストの準備時に、特定のサービスおよび管理グループが適切なインフラストラクチャグループに追加されます。

Lync Server 用の AD の準備時に作成される特定のユニバーサルグループと、インフラストラクチャグループに追加されるサービスおよび管理グループの詳細については、「展開」のドキュメントの「 [Lync server 2013 でのフォレストの準備による変更点](lync-server-2013-changes-made-by-forest-preparation.md)」を参照してください。

<div>


> [!NOTE]  
> Lync Server 2013 は、Windows server 2012 のユニバーサルグループをサポートしています。また、Lync Server 2013 を実行しているサーバーと、ドメインコントローラーの Windows Server 2003 オペレーティングシステムもサポートしています。 ユニバーサルグループのメンバーには、ドメインツリーまたはフォレスト内の任意のドメインの他のグループとアカウントを含めることができます。また、ドメインツリーまたはフォレスト内の任意のドメインでアクセス許可を割り当てることができます。 ユニバーサルグループのサポートを管理者の委任と組み合わせて使用すると、Lync Server の展開の管理が簡単になります。 たとえば、あるドメインを別のドメインに追加して、管理者が両方を管理できるようにする必要はありません。



</div>

</div>

<div>

## <a name="role-based-access-control"></a>役割ベースのアクセス制御

ユニバーサルサービスグループと管理グループの作成、および適切なユニバーサルグループへのサービスと管理グループの追加に加えて、フォレストの準備で役割ベースのアクセス制御 (RBAC) グループも作成されます。 フォレストの準備で作成された特定の RBAC グループの詳細については、「展開」のドキュメントの「 [Lync Server 2013 でのフォレストの準備による変更点](lync-server-2013-changes-made-by-forest-preparation.md)」を参照してください。 RBAC グループの詳細については、「 [Lync Server 2013 の役割ベースのアクセス制御 (RBAC)](lync-server-2013-role-based-access-control-rbac.md)」を参照してください。

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>アクセス制御エントリ (ACE) と継承

フォレストの準備では、プライベート ACE とパブリック ACE の両方が作成され、ユニバーサル グループの ACE が追加されます。 Lync Server によって使用されるグローバル設定コンテナーに特定のプライベート Ace を作成します。 このコンテナーは、Lync Server によってのみ使用され、グローバル設定を格納する場所に応じて、構成コンテナーまたはルートドメインのシステムコンテナーに格納されます。

ドメインの準備ステップでは、ドメイン内のユーザーをホストおよび管理するアクセス許可を与えるアクセス制御エントリ (ACE) をユニバーサル グループに追加します。ドメインの準備で、ドメイン ルートと 3 つの組み込みコンテナー (ユーザー、コンピューター、およびドメイン コントローラー) に対する ACE が作成されます。

フォレストの準備およびドメインの準備で作成および追加されるパブリック Ace の詳細については、「展開」のドキュメントの「 [Lync server 2013 でのフォレストの準備](lync-server-2013-changes-made-by-forest-preparation.md)に加えられた変更」および「 [lync server 2013 のドメイン準備による変更](lync-server-2013-changes-made-by-domain-preparation.md)点」を参照してください。

組織では、セキュリティ リスクを軽減するために Active Directory ドメイン サービス (AD DS) をロックダウンすることがよくあります。 ただし、ロックダウンされた Active Directory 環境では、Lync Server 2013 に必要なアクセス許可を制限することができます。 たとえば、コンテナーと OU からの ACE の削除や、ユーザー、連絡先、InetOrgPerson、コンピューターの各オブジェクトでのアクセス許可の継承の無効化などが挙げられます。 ロックダウンされた Active Directory 環境では、コンテナーと OU のアクセス許可を必要に応じて手動で設定する必要があります。 詳細については、「展開」のドキュメントの「 [Lync Server 2013 でロックダウンされた Active Directory ドメインサービスを準備する](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。

</div>

<div>

## <a name="server-information"></a>サーバー情報

ライセンス認証時に、Lync Server 2013 は、Active Directory ドメインサービス内の次の3つの場所にサーバー情報を公開します。

  - Lync Server 2013 がインストールされている物理コンピューターに対応する各 Active Directory コンピューターオブジェクトのサービス接続ポイント (SCP)。

  - **msRTCSIP-Pools** クラスのコンテナーに作成されるサーバー オブジェクト。

  - トポロジビルダーで指定されている信頼されたサーバー。

</div>

<div>

## <a name="service-connection-points"></a>サービス接続ポイント

Active Directory ドメインサービスの各 Lync Server 2013 オブジェクトには、RTC Services という名前の SCP があります。これには、各コンピューターを識別して、提供されるサービスを指定するいくつかの属性が含まれます。 より重要な SCP 属性には、 *serviceDNSName*、 *serviceDNSNameType*、 *serviceClassname*、および*serviceBindingInformation*があります。 サードパーティ製のアセット管理アプリケーションは、これらの属性とその他の SCP 属性を照会することによって、展開全体でサーバー情報を取得できます。

</div>

<div>

## <a name="active-directory-server-objects"></a>Active Directory サーバー オブジェクト

各 Lync Server 2013 のサーバーの役割には、その役割によって提供されるサービスを定義する属性を持つ、対応する Active Directory オブジェクトがあります。 また、Standard Edition サーバーがアクティブになったとき、または Enterprise Edition プールが作成されたときに、Lync Server 2013 は、 **msRTCSIP**コンテナーに新しい**msRTCSIP**オブジェクトを作成します。 **MsRTCSIP**クラスは、プールの完全修飾ドメイン名 (FQDN) と、プールのフロントエンドおよびバックエンドのコンポーネント間の関連付けを指定します。 (Standard Edition サーバーは、1台のコンピューターにフロントおよびバックエンドが併置されている論理プールと見なされます)。

</div>

<div>

## <a name="trusted-servers"></a>信頼済みのサーバー

Lync Server 2013 では、[信頼されたサーバー] は、トポロジビルダーを実行してトポロジを公開するときに指定されるものです。 公開したトポロジは、すべてのサーバー情報を含めて、中央管理ストアに格納されます。 中央管理ストアで定義されているサーバーのみが信頼されます。 Lync Server 2013 では、信頼されたサーバーは次の条件を満たすものです。

  - サーバーの FQDN が、中央管理ストアに格納されているトポロジに出現する。

  - サーバーが、信頼されている CA からの有効な証明書を提示している。 詳細については、「 [Lync Server 2013 の証明書インフラストラクチャ要件](lync-server-2013-certificate-infrastructure-requirements.md)」を参照してください。

このどちらかの条件が満たされていない場合、サーバーは信頼されず、サーバーとの接続は拒否されます。この二重の要件により、悪意のあるサーバーが有効なサーバーの FQDN を乗っ取ろうとする攻撃を (たとえ攻撃の可能性が低くても) 防ぐことができます。

また、lync server 2013 サーバーと通信するために Microsoft Office Communications Server 2007 R2 および Microsoft Office Communications Server 2007 の展開を有効にするために、Lync Server 2013 は、のリストを保持するためのフォレストの準備中にコンテナーを作成します。以前のリリースの信頼されたサーバー。 次の表は、以前の展開との互換性維持のために作成されるコンテナーを示しています。

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>信頼済みのサーバーのリストと、以前のリリースとの互換性を維持するための Active Directory コンテナー

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>信頼済みのサーバーのリスト</th>
<th>Active Directory コンテナー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition サーバーおよびエンタープライズ プールのフロント エンド サーバー</p></td>
<td><p>RTC サービス/グローバル設定</p></td>
</tr>
<tr class="even">
<td><p>会議サーバー</p></td>
<td><p>RTC サービス/信頼済み MCU</p></td>
</tr>
<tr class="odd">
<td><p>Web コンポーネント サーバー</p></td>
<td><p>RTC サービス/TrustedWebComponentsServers</p></td>
</tr>
<tr class="even">
<td><p>仲介サーバーと Communicator Web Access サーバー、アプリケーション サーバー、レジストラーと QoE、音声ビデオ会議サービス (サードパーティの SIP サーバーを含む)</p></td>
<td><p>RTC サービス/信頼済みサービス</p></td>
</tr>
<tr class="odd">
<td><p>プロキシ サーバー</p></td>
<td><p>Lync Server 2013 は、プロキシサーバーの下位互換性をサポートしていません。</p></td>
</tr>
</tbody>
</table>


以前のリリースの信頼済みサーバーをサポートするには、ベストプラクティスアナライザーツールを実行する必要があります。 ベストプラクティスアナライザーの実行の詳細について[https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633)は、「」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

