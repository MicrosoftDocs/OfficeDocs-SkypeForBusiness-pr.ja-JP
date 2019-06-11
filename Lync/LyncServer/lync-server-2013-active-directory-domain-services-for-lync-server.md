---
title: 'Lync Server 2013: Lync Server 用 Active Directory ドメインサービス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a7dd0a5d5c6d8323abab3a8abfbc5f1025379e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a>Lync Server 2013 用 Active Directory ドメインサービス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-13_

Active Directory ドメインサービスは、Windows Server 2003、Windows Server 2008、Windows Server 2012、Windows Server 2012 R2 ネットワークのディレクトリサービスとして機能します。 Active Directory ドメインサービスは、Microsoft Lync Server 2013 セキュリティインフラストラクチャを構築する基盤としても機能します。 このセクションの目的は、Lync Server 2013 で Active Directory ドメインサービスを使って、IM、Web 会議、メディア、音声の信頼できる環境を作成する方法を説明します。 Active Directory ドメインサービスに対する Lync Server extensions の詳細、および Active directory ドメインサービスの環境の準備については、「展開で[Lync server 2013 用の Active Directory ドメインサービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。documentation. Windows Server ネットワークの Active Directory ドメインサービスの役割の詳細については、使用しているオペレーティングシステムのバージョンのドキュメントを参照してください。

Lync Server 2013 は、次のように Active Directory ドメインサービスを使用して保存します。

  - フォレスト内の Lync Server 2013 を実行しているすべてのサーバーが必要とするグローバル設定。

  - フォレストで Lync Server 2013 を実行しているすべてのサーバーの役割を特定するサービス情報。

  - 一部のユーザー設定。

<div>

## <a name="active-directory-infrastructure"></a>Active Directory インフラストラクチャ

Active Directory のインフラストラクチャ要件には、次のものがあります。

  - ドメイン コントローラーのオペレーティング システム要件

  - ドメインとフォレストの機能レベルの要件

  - グローバル カタログ ドメインの要件

詳細については、展開ドキュメントの「 [Lync Server 2013 の Active Directory インフラストラクチャの要件](lync-server-2013-active-directory-infrastructure-requirements.md)」を参照してください。

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Active Directory ドメインサービスの準備

<div>


> [!NOTE]  
> システムコンテナーの代わりに、構成コンテナーにグローバル設定を展開することをお勧めします。 これにより、セキュリティが強化されることはありませんが、一部の Active Directory ドメインサービストポロジのスケーラビリティが向上する可能性があります。 Microsoft Office Communications Server 2007 から移行していて、システムコンテナーを使っていて、構成コンテナーの使用を計画している場合は、アップグレード準備を行う前に、システムコンテナーの設定を移動する必要があります。 構成コンテナーにシステムコンテナーの設定を移行するには、「Office Communications Server 2007 の<A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>グローバル設定移行ツール」を参照してください。



</div>

Lync Server 2013 を展開する場合、最初の手順として Active Directory ドメインサービスを準備します。 Lync Server 2013 用の Active Directory ドメインサービスの準備は、次の3つの手順で構成されています。

  - **スキーマを準備**します。 このタスクによって、Active Directory ドメインサービスのスキーマが拡張され、Lync Server 2013 に固有のクラスと属性が含まれます。 スキーマの準備の詳細については、展開ドキュメントの「 [Lync Server 2013 での Active Directory スキーマの準備の実行](lync-server-2013-running-schema-preparation.md)」を参照してください。 詳細については、「 [Office Communications server 2007 R2 から Lync Server 2013 に移行する](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)」を参照してください。

  - **フォレストを準備**します。 このタスクでは、フォレストのルートドメインにグローバル設定とオブジェクトを作成し、これらの設定とオブジェクトへのアクセスを管理するユニバーサルサービスと管理グループを作成します。 フォレストの準備について詳しくは、展開ドキュメントで「 [Lync Server 2013 用のフォレストの準備を実行](lync-server-2013-running-forest-preparation.md)する」をご覧ください。

  - **ドメインを準備**します。 このタスクは、必要なアクセス制御エントリ (Ace) をユニバーサルグループに追加します。これにより、ドメイン内でのユーザーのホストと管理のアクセス許可が付与されます。 このタスクは、Lync Server 2013 を実行しているサーバーおよび Lync Server ユーザーが存在するすべてのドメインで展開するすべてのドメインで完了する必要があります。 ドメインの準備について詳しくは、展開ドキュメントで「 [Lync Server 2013 のドメインの準備を実行](lync-server-2013-running-domain-preparation.md)する」をご覧ください。

Active Directory を準備するための完全なプロセスと、各手順を実行するために必要な権限と権限については、展開ドキュメントの「 [Lync Server 2013 の Active directory インフラストラクチャ要件](lync-server-2013-active-directory-infrastructure-requirements.md)」を参照してください。

</div>

<div>

## <a name="universal-groups"></a>ユニバーサル グループ

Lync Server 2013 は、フォレストの準備中に、グローバル設定とサービスにアクセスして管理するためのアクセス許可を持つ、Active Directory ドメインサービス内でさまざまなユニバーサルグループを作成します。 作成されるユニバーサル グループには、次のようなものがあります。

  - **管理グループ**。 これらのグループは、Lync Server ネットワークの基本的な管理者の役割を定義します。 フォレストの準備中に、これらの管理者グループが Lync Server インフラストラクチャグループに追加されます。

  - **サービスグループ**。 これらのグループは、Lync Server によって提供されるさまざまなサービスにアクセスするために必要なサービスアカウントです。

  - **インフラストラクチャグループ**。 これらのグループは、Lync Server インフラストラクチャの特定の領域にアクセスするためのアクセス許可を提供します。 変更したり、ユーザーを直接追加したりしないでください。 フォレストの準備時に、特定のサービス グループと管理グループが、対応するインフラストラクチャ グループに追加されます。

Lync Server 用の広告を準備するときに作成される特定のユニバーサルグループと、インフラストラクチャグループに追加されるサービスと管理グループの詳細については、「microsoft [Lync server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)」を参照してください。展開ドキュメント。

<div>


> [!NOTE]  
> Lync server 2013 2012 では、Lync Server 2013 を実行しているサーバーと、Windows Server 2003 オペレーティングシステムがドメインコントローラーで使用するユニバーサルグループがサポートされています。 ユニバーサルグループのメンバーには、ドメインツリーまたはフォレスト内の任意のドメインの他のグループとアカウントを含めることができ、ドメインツリーまたはフォレスト内の任意のドメインでアクセス許可を割り当てることができます。 ユニバーサルグループのサポートは、管理者の委任と組み合わせて、Lync Server の展開の管理を簡素化します。 たとえば、あるドメインを別のドメインに追加して、管理者が両方を管理できるようにする必要はありません。



</div>

</div>

<div>

## <a name="role-based-access-control"></a>役割ベースのアクセス制御

ユニバーサル サービス グループと管理グループを作成し、サービス グループと管理グループを対応するユニバーサル グループに追加することに加えて、フォレストの準備では役割ベースのアクセス制御 (RBAC) グループも作成されます。 フォレストの準備によって作成された特定の RBAC グループの詳細については、展開ドキュメントの「 [Lync Server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)」を参照してください。 RBAC グループの詳細については、「 [Lync Server 2013 の役割ベースのアクセス制御 (RBAC)](lync-server-2013-role-based-access-control-rbac.md)」を参照してください。

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>アクセス制御エントリ (ACE) と継承

フォレストの準備では、プライベート ACE とパブリック ACE の両方が作成され、ユニバーサル グループの ACE が追加されます。 Lync Server で使用されるグローバル設定コンテナーに特定のプライベート Ace を作成します。 このコンテナーは、Lync Server によってのみ使用され、グローバル設定を保存する場所に応じて、構成コンテナーまたはルートドメイン内のシステムコンテナーのいずれかにあります。

ドメインの準備ステップでは、ドメイン内のユーザーをホストおよび管理するアクセス許可を与えるアクセス制御エントリ (ACE) をユニバーサル グループに追加します。ドメインの準備で、ドメイン ルートと 3 つの組み込みコンテナー (ユーザー、コンピューター、およびドメイン コントローラー) に対する ACE が作成されます。

フォレストの準備とドメインの準備によって作成および追加されたパブリック Ace の詳細については、「 [Lync server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)」および「展開の[lync server 2013 でのドメインの準備](lync-server-2013-changes-made-by-domain-preparation.md)によって行われた変更」を参照してください。documentation.

組織は、セキュリティリスクを軽減するために Active Directory ドメインサービス (AD DS) をロックダウンすることがよくあります。 ただし、ロックダウンされた Active Directory 環境では、Lync Server 2013 で必要なアクセス許可を制限できます。 たとえば、コンテナーと OU からの ACE の削除や、ユーザー、連絡先、InetOrgPerson、コンピューターの各オブジェクトでのアクセス許可の継承の無効化などが挙げられます。 ロックダウンされた Active Directory 環境では、アクセス許可を必要とするコンテナーと Ou に対して手動でアクセス許可を設定する必要があります。 詳細については、展開ドキュメントの「 [Lync Server 2013 でロックダウン Active Directory ドメインサービスを準備する](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。

</div>

<div>

## <a name="server-information"></a>サーバー情報

ライセンス認証の際に、Lync Server 2013 は、Active Directory ドメインサービスの次の3つの場所にサーバー情報を公開します。

  - Lync Server 2013 がインストールされている物理コンピューターに対応した各 Active Directory コンピューターオブジェクトのサービス接続ポイント (SCP)。

  - **msRTCSIP-Pools** クラスのコンテナーに作成されるサーバー オブジェクト。

  - トポロジビルダーで指定された信頼できるサーバー。

</div>

<div>

## <a name="service-connection-points"></a>サービス接続ポイント

Active Directory ドメインサービス内の各 Lync Server 2013 オブジェクトには、RTC サービスという SCP があります。これには、各コンピューターを識別し、提供するサービスを指定するための多数の属性が含まれます。 さらに重要な SCP 属性には、 *serviceDNSName*、 *serviceDNSNameType*、 *serviceClassname*、および*serviceBindingInformation*があります。 サードパーティの資産管理アプリケーションは、このような SCP の属性を照会することによって、展開を通じてサーバーの情報を取得できます。

</div>

<div>

## <a name="active-directory-server-objects"></a>Active Directory Server オブジェクト

各 Lync Server 2013 サーバーの役割には、その役割によって提供されるサービスを定義する属性を持つ Active Directory オブジェクトがそれぞれ含まれています。 また、Standard Edition サーバーがアクティブ化されたとき、または Enterprise Edition プールを作成したときに、Lync Server 2013 は、 **msrtcsip-userenabled true**コンテナーに新しい**msrtcsip-userenabled true**オブジェクトを作成します。 **Msrtcsip-userenabled true**クラスは、プールの完全修飾ドメイン名 (FQDN) を、プールのフロントエンドコンポーネントとバックエンドコンポーネントの間の関連付けと共に指定します。 (Standard Edition サーバーは、フロントエンドとバックエンドが1台のコンピュータに併置されている論理プールと見なされます)。

</div>

<div>

## <a name="trusted-servers"></a>信頼済みのサーバー

Lync Server 2013 の [信頼済みサーバー] は、トポロジビルダーを実行してトポロジを公開するときに指定されたものです。 公開したトポロジは、すべてのサーバー情報を含めて、中央管理ストアに格納されます。 中央管理ストアで定義されているサーバーのみが信頼されます。 Lync Server 2013 の信頼できるサーバーは、次の条件を満たしているサーバーです。

  - サーバーの FQDN が、中央管理ストアに格納されているトポロジに出現する。

  - サーバーが、信頼されている CA からの有効な証明書を提示している。 詳細については、「 [Lync Server 2013 の証明書インフラストラクチャの要件](lync-server-2013-certificate-infrastructure-requirements.md)」を参照してください。

このどちらかの条件が満たされていない場合、サーバーは信頼されず、サーバーとの接続は拒否されます。この二重の要件により、悪意のあるサーバーが有効なサーバーの FQDN を乗っ取ろうとする攻撃を (たとえ攻撃の可能性が低くても) 防ぐことができます。

さらに、Microsoft Office Communications Server 2007 R2 および Microsoft Office Communications Server 2007 の展開を有効にして、Lync Server 2013 サーバーと通信するために、Lync Server 2013 はフォレストの作成時にコンテナーを作成します。以前のリリース向けの信頼されたサーバー。 次の表は、以前の展開との互換性維持のために作成されるコンテナーを示しています。

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>以前のリリースとの互換性を確保するために、信頼されたサーバーの一覧とその Active Directory コンテナー

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


以前のリリースの信頼されたサーバーをサポートするには、ベストプラクティスアナライザーツールを実行する必要があります。 ベストプラクティスアナライザーの実行の詳細について[http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)は、を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

