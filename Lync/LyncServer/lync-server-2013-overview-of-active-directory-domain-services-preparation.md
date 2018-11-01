---
title: 'Lync Server 2013: Active Directory ドメイン サービスの準備の概要'
TOCTitle: Active Directory ドメイン サービスの準備の概要
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48273602
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Active Directory ドメイン サービスの準備の概要

 

_**トピックの最終更新日:** 2015-03-09_

Lync Server 2013 展開用に Active Directory ドメイン サービス を準備するには、3 つのステップを決められた順序で実行する必要があります。

次の表に、 Lync Server 用に AD DS を準備するために必要なステップを示します。

### Active Directory の準備のステップ

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>ステップ</th>
<th>説明</th>
<th>実行場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Lync Server 2013 での Active Directory スキーマの準備</a></p></td>
<td><p>Lync Server が使用する新しいクラスと属性を追加して、Active Directory スキーマを拡張する。</p>
<p>Lync Server を展開する場所のフォレストごとに 1 回実行する。</p></td>
<td><p>Lync Server が展開される各フォレストのルート ドメイン内のスキーマ マスターに対して実行します。</p>

> [!NOTE]
> スキーマ マスターでのアクセス許可を持っている場合は、ルート ドメインでこのステップを実行する必要はありませんが、そのルート ドメインの Schema Admins グループのメンバーに、またスキーマ マスターでの Enterprise Admins グループのメンバーになっている必要があります。リソース フォレスト トポロジでは、ユーザー フォレストではなく、リソース フォレストのみでこのステップを実行します。中央フォレスト トポロジでは、ユーザー フォレストではなく、中央フォレストのみでこのステップを実行します。

</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Lync Server 2013 でのフォレストの準備</a></p></td>
<td><p>Lync Server で使用されるグローバル設定とユニバーサル グループを作成する。</p>
<p>Lync Server を展開する場所のフォレストごとに 1 回実行する。</p></td>
<td><p>Lync Server が展開される各フォレストのルート ドメイン。このステップを実行するには、Enterprise Admins グループのメンバーになっている必要があります。</p>

> [!NOTE]
> リソース フォレスト トポロジでは、ユーザー フォレストではなく、リソース フォレストのみでこのステップを実行します。中央フォレスト トポロジでは、ユーザー フォレストではなく、中央フォレストのみでこのステップを実行します。


</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Lync Server 2013 のドメインの準備</a></p></td>
<td><p>ユニバーサル グループのメンバーが使用するオブジェクトに対するアクセス許可を追加する。</p>
<p>ユーザー ドメインまたはサーバー ドメインあたり 1 回実行する。</p>

> [!NOTE]
> Lync Server 2010 から Lync Server 2013 に移行する場合には、展開ウィザードに、ドメインの準備が既に完了していることが示されます。ドメインの準備を再度実行する必要はありません。アクセス許可は Lync Server 2010 から Lync Server 2013 に変更されていません。

<td><p>Lync Server が展開される各ドメイン内のメンバー サーバー。このステップを実行するには、Domain Admins グループのメンバーになっている必要があります。</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 は Lync Server 2010 と同様、構成情報の大部分を、 Office Communications Server 2007 R2 の場合のように AD DS ではなく、 中央管理ストアに保管します。ただし、以下の情報は AD DS に保管されます。

  - **スキーマ拡張**:
    
      - ユーザー オブジェクトの拡張
    
      - 下位互換性を確保するための Office Communications Server 2007 R2 クラスの拡張

<!-- end list -->

  - **データ** ( Lync Server 拡張スキーマ クラスと既存のスキーマ クラスに保存):
    
      - ユーザーの SIP URI (Uniform Resource Identifier) と他のユーザー設定
    
      - リソース グループや会議アテンダントなどのアプリケーションの連絡先オブジェクト
    
      - 中央管理ストアへのポインター
    
      - Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)

Lync Server 2013 では、RTCUniversalServerAdmins ユニバーサル グループのメンバーにセットアップ アクセス許可を与えることによってセットアップおよび管理を委任することができます。このグループのメンバーは、(サーバーがトポロジに追加され、公開され、有効にされた後に) ローカル サーバーで Lync Server 2013 をインストールしてアクティブ化することができます。委任されるユーザーは、 Lync Server 2013 をインストールしてアクティブ化するコンピューターのローカル管理者である必要がありますが、Domain Admins グループのメンバーである必要はありません。また、フォレストの準備中に作成したユニバーサル グループのメンバーが Domain Admins グループのメンバーでなくても指定された組織単位 (OU) 内のオブジェクトにアクセスできるよう、それらのオブジェクトに対するアクセス許可を付与することもできます。

Lync Server 2013 の新規展開の場合は、グローバル設定を構成コンテナーに保管する必要があります。旧バージョンからアップグレードし、システム コンテナーにまだグローバル設定が残されている場合、そのシステム コンテナーは引き続きサポートされます。

## 関連項目

#### 概念

[Lync Server 2013 での Active Directory スキーマの準備](lync-server-2013-preparing-the-active-directory-schema.md)  
[Lync Server 2013 が使用する Active Directory のスキーマ拡張、クラス、属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  

#### その他のリソース

[Lync Server 2013 でのフォレストの準備](lync-server-2013-preparing-the-forest.md)  
[Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)

