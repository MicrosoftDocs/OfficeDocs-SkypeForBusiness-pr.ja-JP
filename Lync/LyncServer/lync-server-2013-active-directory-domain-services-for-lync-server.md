---
title: Lync Server 2013 用の Active Directory ドメイン サービス
TOCTitle: Lync Server 2013 用の Active Directory ドメイン サービス
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59679285
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 用の Active Directory ドメイン サービス

 

_**トピックの最終更新日:** 2016-12-08_

Active Directory ドメイン サービスは、Windows Server 2003、Windows Server 2008、Windows Server 2012、および Windows Server 2012 R2 のネットワークのディレクトリ サービスとして機能します。また、Active Directory ドメイン サービスは、Microsoft Lync Server 2013 のセキュリティ インフラストラクチャを構築するための基盤にもなります。このセクションの目的は、Lync Server 2013 で Active Directory ドメイン サービスを使って、IM、Web 会議、メディア、および音声用の信頼できる環境を構築する方法を説明することです。Active Directory ドメイン サービスに対する Lync Server の拡張機能と、Active Directory ドメイン サービスの環境の準備について詳しくは、展開のドキュメントの「[Lync Server 2013 用の Active Directory ドメイン サービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」をご覧ください。Windows Server のネットワークにおける Active Directory ドメイン サービスの役割について詳しくは、お使いのバージョンのオペレーティング システムのドキュメントをご覧ください。

Lync Server 2013 では、Active Directory ドメイン サービスを使って次の内容が保存されます。

  - フォレスト内で Lync Server 2013 を実行しているすべてのサーバーに必要なグローバル設定。

  - フォレスト内で Lync Server 2013 を実行しているすべてのサーバーの役割を識別するサービス情報。

  - 一部のユーザー設定。

## Active Directory インフラストラクチャ

Active Directory のインフラストラクチャ要件には、次のようなものがあります。

  - ドメイン コントローラーのオペレーティング システム要件

  - ドメインとフォレストの機能レベルの要件

  - グローバル カタログ ドメインの要件

詳しくは、展開のドキュメントの「[Lync Server 2013 に関する Active Directory インフラストラクチャの要件](lync-server-2013-active-directory-infrastructure-requirements.md)」をご覧ください。

## Active Directory ドメイン サービスの準備

> [!NOTE]
> グローバル設定はシステム コンテナーではなく構成コンテナーに展開することをお勧めします。これによってセキュリティが向上するわけではありませんが、一部の Active Directory ドメイン サービスのトポロジではスケーラビリティが向上することがあります。Microsoft Office Communications Server 2007 から移行する場合で、それまで使用していたシステム コンテナーから構成コンテナーに切り替える予定がある場合は、アップグレードの準備をする前に、システム コンテナーの設定を移動する必要があります。システム コンテナーの設定を構成コンテナーに移行するには、「Office Communications Server 2007 のグローバル設定移行ツール (英語)」(<a href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</a>) をご覧ください。


Lync Server 2013 を展開するための最初のステップは、Active Directory ドメイン サービスを準備することです。Lync Server 2013 の Active Directory ドメイン サービスの準備は、次の 3 つのステップから成ります。

  - **スキーマの準備**: Active Directory ドメイン サービスのスキーマを拡張して、Lync Server 2013 固有のクラスと属性を含めます。スキーマの準備について詳しくは、展開のドキュメントの「[Lync Server 2013 での Active Directory スキーマの準備の実行](lync-server-2013-running-schema-preparation.md)」をご覧ください。詳しくは、「[Office Communications Server 2007 R2 から Lync Server 2013 への移行](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)」をご覧ください。

  - **フォレストの準備**: フォレストのルート ドメインのグローバル設定とオブジェクトを、これらの設定とオブジェクトへのアクセスを管理するユニバーサル サービス グループおよびユニバーサル管理グループと共に作成します。フォレストの準備について詳しくは、展開のドキュメントの「[Lync Server 2013 でのフォレストの準備の実行](lync-server-2013-running-forest-preparation.md)」をご覧ください。

  - **ドメインの準備**: ドメイン内のユーザーをホストおよび管理するアクセス許可を与えるアクセス制御エントリ (ACE) をユニバーサル グループに追加します。ドメインの準備は、Lync Server 2013 を実行するサーバーを展開するすべてのドメイン、および Lync Server ユーザーが存在するすべてのドメインで実行する必要があります。ドメインの準備について詳しくは、展開のドキュメントの「[Lync Server 2013 のドメイン準備手続き](lync-server-2013-running-domain-preparation.md)」をご覧ください。

Active Directory を準備するための全体のプロセス、および各ステップの実行に必要な権限とアクセス許可の概要については、展開のドキュメントの「[Lync Server 2013 に関する Active Directory インフラストラクチャの要件](lync-server-2013-active-directory-infrastructure-requirements.md)」をご覧ください。

## ユニバーサル グループ

フォレストの準備時に、Lync Server 2013 ではグローバル設定とサービスにアクセスして管理する権限を持つさまざまなユニバーサル グループが Active Directory ドメイン サービス内に作成されます。作成されるユニバーサル グループには、次のようなものがあります。

  - **管理グループ**: Lync Server ネットワークの基本的な管理者の役割を定義するグループです。フォレストの準備時に、これらの管理者のグループが Lync Server インフラストラクチャ グループに追加されます。

  - **サービス グループ**: Lync Server が提供するさまざまなサービスにアクセスするために必要なサービス アカウントのグループです。

  - **インフラストラクチャ グループ**: Lync Server インフラストラクチャの特定の領域にアクセスする許可を与えるグループです。このグループは、管理グループのコンポーネントとして機能します。変更したり、ユーザーを直接追加したりしないでください。フォレストの準備時に、特定のサービス グループと管理グループが、対応するインフラストラクチャ グループに追加されます。

Lync Server の Active Directory の準備時に作成される個々のユニバーサル グループ、およびインフラストラクチャ グループに追加されるサービス グループと管理グループの詳細については、展開のドキュメントの「[Lync Server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)」をご覧ください。

> [!NOTE]
> Lync Server 2013 は、Lync Server 2013 を実行するサーバーでは Windows Server 2012、またドメイン コントローラーでは Windows Server 2003 オペレーティング システムのユニバーサル グループをサポートしています。ユニバーサル グループのメンバーには、ドメイン ツリーまたはフォレストの任意のドメインから他のグループやアカウントを追加できます。また、ドメイン ツリーまたはフォレストの任意のドメインのアクセス許可を割り当てることができます。ユニバーサル グループのサポートと、管理者の委任が組み合わさることで、Lync Server 展開の管理が簡略化されます。たとえば、ドメインを別のドメインに追加しなくても、管理者が両方のドメインを管理できるようになります。


## 役割ベースのアクセス制御

ユニバーサル サービス グループと管理グループを作成し、サービス グループと管理グループを対応するユニバーサル グループに追加することに加えて、フォレストの準備では役割ベースのアクセス制御 (RBAC) グループも作成されます。フォレストの準備で作成される個々の RBAC グループについて詳しくは、展開のドキュメントの「[Lync Server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)」をご覧ください。RBAC グループについて詳しくは、「[Lync Server 2013 の役割ベースのアクセス制御 (RBAC)](lync-server-2013-role-based-access-control-rbac.md)」をご覧ください。

## アクセス制御エントリ (ACE) と継承

フォレストの準備では、プライベート ACE とパブリック ACE の両方が作成され、ユニバーサル グループの ACE が追加されます。Lync Server で使用されるグローバル設定コンテナーに対して特定のプライベート ACE が作成されます。このコンテナーは Lync Server のみで使用され、グローバル設定の保存場所に応じて、ルート ドメインの構成コンテナーまたはシステム コンテナーに配置されます。

ドメインの準備ステップでは、ドメイン内のユーザーをホストおよび管理するアクセス許可を与えるアクセス制御エントリ (ACE) をユニバーサル グループに追加します。ドメインの準備で、ドメイン ルートと 3 つの組み込みコンテナー (ユーザー、コンピューター、およびドメイン コントローラー) に対する ACE が作成されます。

フォレストの準備およびドメインの準備で作成および追加されるパブリック ACE について詳細しくは、展開のドキュメントの「[Lync Server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)」および「[Lync Server 2013 でのドメインの準備によって加えられる変更](lync-server-2013-changes-made-by-domain-preparation.md)」をご覧ください。

組織では、セキュリティ リスクを軽減するために Active Directory ドメイン サービス (AD DS) をロックダウンすることがよくあります。しかし、ロックダウンされた Active Directory 環境では、Lync Server 2013 に必要なアクセス許可が制限されることがあります。たとえば、コンテナーと OU からの ACE の削除や、ユーザー、連絡先、InetOrgPerson、コンピューターの各オブジェクトでのアクセス許可の継承の無効化などが挙げられます。ロックダウンされた Active Directory 環境では、コンテナーと OU のアクセス許可を必要に応じて手動で設定する必要があります。詳しくは、展開のドキュメントの「[Lync Server 2013 でのロックダウンされた Active Directory ドメイン サービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」をご覧ください。

## サーバー情報

アクティブ化時に、Lync Server 2013 は Active Directory ドメイン サービス内の次の 3 つの場所にサーバー情報を発行します。

  - Lync Server 2013 がインストールされている物理的なコンピューターに対応する各 Active Directory コンピューター オブジェクトのサービス接続ポイント (SCP)。

  - **msRTCSIP-Pools** クラスのコンテナーに作成されるサーバー オブジェクト。

  - トポロジ ビルダーで指定された信頼済みのサーバー。

## サービス接続ポイント

Active Directory ドメイン サービス 内の各 Lync Server 2013 オブジェクトには、RTC サービスと呼ばれる SCP があります。この RTC サービスには、各コンピューターを識別し、コンピューターが提供するサービスを指定する多数の属性が含まれています。SCP の属性の中でも重要なのが *serviceDNSName*、*serviceDNSNameType*、*serviceClassname*、および *serviceBindingInformation* です。サードパーティの資産管理アプリケーションでは、これらの属性や SCP の他の属性に対するクエリを実行し、展開全体にわたるサーバー情報を取得できます。

## Active Directory サーバー オブジェクト

各 Lync Server 2013 のサーバーの役割には対応する Active Directory オブジェクトがあり、そのオブジェクトの属性によって、役割が提供するサービスが定義されます。また、Standard Edition サーバーのアクティブ化時、または Enterprise Edition プールの作成時に、Lync Server 2013 は **msRTCSIP-Pools** コンテナーに新しい **msRTCSIP-Pool** オブジェクトを作成します。**msRTCSIP-Pool** クラスは、プールの完全修飾ドメイン名 (FQDN) と共に、プールのフロント エンド コンポーネントとバック エンド コンポーネントの間の関連付けを指定します (Standard Edition サーバーは、フロント エンドとバック エンドが 1 台のコンピューター上に併置された論理プールと見なされます)。

## 信頼済みのサーバー

Lync Server 2013 では、信頼済みのサーバーとは、トポロジ ビルダーを実行してトポロジを公開するときに指定されるサーバーです。公開したトポロジは、すべてのサーバー情報を含めて、中央管理ストアに格納されます。中央管理ストアで定義されているサーバーのみが信頼されます。Lync Server 2013 では、信頼済みのサーバーは以下の条件を満たしているサーバーです。

  - サーバーの FQDN が、中央管理ストアに格納されているトポロジに出現する。

  - サーバーが、信頼されている CA からの有効な証明書を提示している。詳しくは、「[Lync Server 2013 の証明書インフラストラクチャの要件](lync-server-2013-certificate-infrastructure-requirements.md)」をご覧ください。

このどちらかの条件が満たされていない場合、サーバーは信頼されず、サーバーとの接続は拒否されます。この二重の要件により、悪意のあるサーバーが有効なサーバーの FQDN を乗っ取ろうとする攻撃を (たとえ攻撃の可能性が低くても) 防ぐことができます。

さらに、Microsoft Office Communications Server 2007 R2 展開および Microsoft Office Communications Server 2007 展開で Lync Server 2013 サーバーと通信できるように、Lync Server 2013 ではフォレストの準備時に、以前のリリースの信頼済みのサーバーのリストを保持するためのコンテナーが作成されます。次の表は、以前の展開との互換性維持のために作成されるコンテナーを示しています。

### 信頼済みのサーバーのリストと、以前のリリースとの互換性を維持するための Active Directory コンテナー

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
<td><p>Lync Server 2013 ではプロキシ サーバーの下位互換性はサポートされない</p></td>
</tr>
</tbody>
</table>


以前のリリースの信頼済みのサーバーをサポートするには、下位互換性ツールを実行する必要があります。ベスト プラクティス アナライザーの実行について詳しくは、[http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633) をご覧ください。

