---
title: ID、スコープ、およびテナント
TOCTitle: ID、スコープ、およびテナント
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56270108
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ID、スコープ、およびテナント

 

_**トピックの最終更新日:** 2015-06-22_

Skype for Business Online の管理に使用する Windows PowerShell コマンドレットの多くでは、管理しようとする項目に対して固有の情報を指定する必要があります。たとえば、[Set-CsUserAcp](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUserAcp) コマンドレット実行する場合には、管理しようとするユーザーを指定する必要があります。このことには意味があり、どのユーザー アカウントを管理するかをコマンドレットに具体的に通知しないと、**Set-CsUserAcp** コマンドレットでは、どのユーザーの電話会議の情報を変更する必要があるかが不明になります。このような理由により、**Set-CsUserAcp** コマンドレットを実行するたびに、Identity パラメーターを含め、その後に変更するユーザー アカウントの ID を続ける必要があります。

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

Identity という用語が常にユーザー アカウントの ID を指す場合は、混乱が生じる原因にはほとんどなりません。人物 (ユーザー、連絡先など) を扱う場合は、Identity は個々のユーザー自身を指します。ただし、ユーザーアカウント以外の項目にも Identity があります。Skype for Business Online サービスのコンポーネント、つまりポリシー、構成設定などを扱う場合、Identity という用語は少し異なる内容を意味します。たとえば、次のコマンドの場合を考えます。

    Get-CsMeetingConfiguration -Identity "global"

この場合、Identity "global" は会議構成設定のスコープを指します。スコープは、Skype for Business Online (および Lync Server) において管理の範囲を指定するために使用される用語です。既定では、ポリシーと設定には常にグローバル スコープがあります。初めて Skype for Business Online アカウントを設定する場合、既定では、グローバル ポリシーと設定 (グローバルな会議構成設定、グローバルな外部アクセス ポリシー、グローバルなダイヤル プランなど) のコレクションを使用します。

これらのグローバル ポリシーと設定は、すべてのユーザーとすべてのコンポーネントが常に何らかの方法で確実に管理されるように、Microsoft Lync Server 2010 で導入されました。このことは、Microsoft Office Communicator 2007 R2 では必ずしも該当しません。システムにアクセスした方法に応じて、(通常はグループ ポリシーをユーザー アカウントに適用できなかったことが原因で) 最終的に大部分が管理されていない状態になる可能性があります。対照的に、Lync Server および Skype for Business Online においては、管理されないまま残るものはありません。これは、「他のすべての代わりに」グローバルなポリシーと設定が常に適用されるためです。

ここで、「他のすべての代わりに」はどういう意味であるかが問題になりますが、Skype for Business Online の場合は、タグ スコープ、つまり管理の範囲でポリシーを作成できます。タグ スコープ (別名、ユーザーごとのスコープ) で作成されるポリシーは、グローバル スコープで作成されるポリシーよりも優先されます。つまり、ユーザーごとのポリシーはグローバル ポリシーよりも常に優先されます。たとえば、2 つの外部ユーザー アクセス ポリシーを使用するとします。グローバル ポリシーでは、Windows Live などのパブリック インスタント メッセージング (IM) プロバーダー上にアカウントを所有するユーザーとの通信が禁止されています。ユーザーごとのポリシーである AllowPublicIMCommunication では、パブリック IM プロバイダーとの通信が許可されています。

また、Ken Myer と Pilar Ackerman という 2 人のユーザーも存在するとします。Ken Myer にはユーザーごとのポリシーが割り当てられています。Pilar Ackerman にはユーザーごとのポリシーが割り当てられていません。つまり、グローバル外部アクセス ポリシーにより管理されています。次の表に、どのユーザーがパブリック IM プロバイダーと通信できるかを示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ポリシー設定</th>
<th>Ken Myer</th>
<th>Pilar Ackerman</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>パブリック IM プロバイダーのグローバル ポリシー設定</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>パブリック IM プロバイダーのユーザーごとのポリシー設定</p></td>
<td><p>はい</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>ユーザーがパブリック IM プロバイダーと通信できるかどうか</p></td>
<td><p>はい</p></td>
<td><p>いいえ</p></td>
</tr>
</tbody>
</table>


上記からわかるように、Ken Myer はパブリック IM プロバイダーと通信できます。これは、Ken Myer に割り当てられているユーザーごとのポリシーの設定が、グローバル ポリシーの設定よりも優先されるためです。Pilar Ackerman はパブリック IM プロバイダーと通信することはできません。これは、Pilar Ackerman はグローバル ポリシーによって管理されていて、グローバル ポリシーではそのような通信が禁止されているためです。

ユーザーごとのポリシーは、Office 365 サポートが作成する必要があります。ポリシーが作成された後、適切な **Grant-Cs** コマンドレット ([Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) など) を使用するとユーザーにポリシーを割り当てることができます。ユーザーごとのポリシーは、ポリシー Identity の先頭が常にタグ **プレフィックス**であるため、容易に識別できます。次に例を示します。

    Identity : tag:AllowPublicIMCommunication

> [!NOTE]
> タグ <strong>プレフィックス</strong>の日付は、Lync Server 2010 の初期展開の日に遡ります。当時、ユーザーごとのポリシーはタグ ポリシーと呼ばれ、タグ <strong>プレフィックス</strong>により識別されました。現在、これらのポリシーはより正確にユーザーごとのポリシーと呼ばれ、タグ スコープはより正確にユーザーごとのスコープと呼ばれています。ただし、技術上の理由により、タグ <strong>プレフィックス</strong>は変更されていません。


Skype for Business Online および Windows PowerShell を操作する際に使用されるもう 1 つの重要な用語としては、テナントがあります。Skype for Business Online アカウントを設定すると、新しい展開環境にはテナント ID 番号が割り当てられます。これは、次のようなグローバル一意識別子です。

    bf19b7db-6960-41e5-a139-2aa373474354

コマンドレットを実行する際にテナント ID を入力する必要がある Skype for Business Online のコマンドレットはごくわずかです。1 つのテナントにログオンしていて、そのテナントしか所有していない場合であっても、テナント ID を入力する必要があります。ただし、テナント ID を記憶しておく必要はありません。次の Windows PowerShell コマンドを実行すれば、いつでもテナント ID を取得できます。

    Get-CsTenant | Select-Object TenantId

当然ながら、グローバル スコープとユーザーごとのスコープ (タグ スコープ) の相違点などの項目を知っておくことは、完全な習得までの途中にすぎません。これらのスコープを使用できるタイミング (または場合によっては使用できる条件) を知っておくことも重要です。同じことが、ID やテナント パラメーターについても言えます。以降のトピックでは、さまざまな Skype for Business Online のコマンドレットで、ID、スコープ、およびテナント パラメーターを使用する方法について説明します。

  - [グローバル スコープのみを使用するコマンドレット](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [グローバル スコープとタグ スコープを使用するコマンドレット](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [ユーザー ID を使用するコマンドレット](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [ユーザー ID とタグ スコープを使用するコマンドレット](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Tenant パラメーターを使用するコマンドレット](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [会議プロバイダー ID を使用するコマンドレット](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Scope や Identity を使用しないコマンドレット](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

