---
title: Skype for Business Online の id、スコープ、テナント
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a759c53b717cbaf1ecdb747d5cb01e94b305f52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>Skype for Business Online の id、スコープ、テナント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-03-09_

Skype for Business Online を管理するために使用される Windows PowerShell コマンドレットの多くは、管理する項目について特に明確にしておく必要があります。 たとえば、 [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)コマンドレットを実行する場合は、管理しようとしているユーザーを指定する必要があります。 これは理にかなっています。 管理するユーザーアカウントをコマンドレットに明示的に指定し**** ていない限り、ユーザーの電話会議情報を変更する必要があるかどうかを指定することはできません。 このため、 **Set-CsUserAcp**コマンドレットを実行するたびに、id パラメーターを含める必要があります。その後に、変更するユーザーアカウントの id を指定する必要があります。

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

用語*id*がユーザーアカウントの id を常に参照している場合は、混乱の原因になることはほとんどありません。 ユーザー (ユーザー、連絡先など) を扱う場合、Id は個々のユーザーを参照します。 ただし、ユーザーアカウント以外のアイテムにも Id があります。 Skype for Business Online サービスのコンポーネント (ポリシー、構成設定など) を処理している場合は、ユーザーの用語によって若干の違いがあります。 たとえば、次のコマンドを考えてみます。

    Get-CsMeetingConfiguration -Identity "global"

この場合、Id "global" は、会議の構成設定の範囲を指します。 *スコープ*は、管理の球体を指定するために Skype For business Online (および Lync Server) で使用される用語です。 既定では、ポリシーと設定は常にグローバルスコープを持ちます。 初めて Skype for Business Online アカウントを設定すると、グローバルなポリシーと設定のコレクション (グローバル会議構成の設定、グローバル外部アクセスポリシー、グローバルダイヤルプランなど) が使用されます。

これらのグローバルポリシーと設定は、Microsoft Lync Server 2010 で導入されました。すべてのユーザーとすべてのコンポーネントを常に何らかの方法で管理することができます。 これは、Microsoft Office Communicator 2007 R2 では必ずしも当てはまりません。 システムにアクセスした方法によっては、ほぼ管理されていない状態で終了する可能性があります (通常は、グループポリシーがユーザーアカウントに適用されていないためです)。 一方、Lync Server および Skype for Business Online では、管理されていないものは何も残りません。 これは、他の項目の代わりにグローバルポリシーと設定が常に適用されるためです。

"Else の代わりに" とは何を意味していますか? Skype for Business Online の場合、*タグのスコープ*または管理の球体でポリシーを作成することができます。 タグのスコープ (*ユーザーごとのスコープ*とも呼ばれます) で作成されたポリシーは、グローバルスコープで作成されたポリシーよりも優先されます。 つまり、ユーザーごとのポリシーは常にグローバルポリシーよりも優先されます。 たとえば、2つの外部ユーザーアクセスポリシーがある場合があります。 グローバルポリシーを使用すると、ユーザーは、Windows Live などのパブリックインスタントメッセージング (IM) プロバイダーのアカウントを持っているユーザーとの通信を禁止できます。 ユーザーごとのポリシー (AllowPublicIMCommunication) では、パブリック IM プロバイダーとの通信が可能になります。

また、Ken Myer と Pilar Ackerman という2人のユーザーがいる場合もあります。 Ken Myer には、ユーザーごとのポリシーが割り当てられています。 Pilar Ackerman には、ユーザーごとのポリシーが割り当てられていません。つまり、彼女はグローバル外部アクセスポリシーによって管理されます。 次の表は、パブリック IM プロバイダーと通信できるユーザー (存在する場合) を示しています。


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
<td><p>パブリック IM プロバイダーのグローバルポリシー設定</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>パブリック IM プロバイダーのユーザーごとのポリシー設定</p></td>
<td><p>はい</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>ユーザーはパブリック IM プロバイダーと通信できます</p></td>
<td><p>はい</p></td>
<td><p>いいえ</p></td>
</tr>
</tbody>
</table>


ご覧のとおり、Ken Myer はパブリック IM プロバイダーとの通信を許可されています。 これは、ユーザーに割り当てられているユーザーごとのポリシーの設定がグローバルポリシーの設定を上書きするためです。 Pilar Ackerman はパブリック IM プロバイダーと通信できません。 これは、ユーザーがグローバルポリシーによって管理されており、グローバルポリシーでそのような通信が禁止されているためです。

Office 365 サポートでは、ユーザーごとのポリシーを作成する必要があります。 ポリシーが作成された後、適切な**grant-Cs**コマンドレット ( [grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)など) を使用して、ポリシーをユーザーに割り当てることができます。 ポリシー Id は常にタグ**プレフィックス**で始まるため、ユーザーごとのポリシーを識別するのは簡単です。 次に例を示します。

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> タグ<STRONG>プレフィックス</STRONG>の日付は、Lync Server 2010 の最早開発日に戻されます。 この日に、ユーザーごとのポリシーは<EM>タグポリシー</EM>として参照され、タグ<STRONG>プレフィックス</STRONG>によって識別されました。 これらのポリシーは、<EM>ユーザーごとのポリシー</EM>としてより正確に示されるようになりました。タグスコープは、<EM>ユーザーごとのスコープ</EM>としてより正確に参照されます。 ただし、技術的な理由から、タグ<STRONG>プリフィックス</STRONG>は変更されませんでした。



</div>

Skype for Business Online と Windows PowerShell を操作するときに使用される別のキー用語は、*テナント*です。 Skype for Business Online アカウントを設定すると、新しい展開には、次のようなグローバル一意識別子 (GUID) であるテナント ID 番号が割り当てられます。

    bf19b7db-6960-41e5-a139-2aa373474354

Skype for Business Online のコマンドレットの一部では、コマンドレットを実行するたびにテナント ID を入力する必要があります。 1つのテナントのみにログオンしている場合でも、テナント ID を入力する必要があります。 しかし、テナント ID を覚える必要はありません。 テナント ID は、次の Windows PowerShell コマンドを実行すると、いつでも取得できます。

    Get-CsTenant | Select-Object TenantId

もちろん、グローバルスコープとユーザーごとのスコープ (またはタグのスコープ) の違いがわかっている場合は、半分の戦いにすぎません。 また、どのような場合にも、これらのスコープを使用できるかどうかを知っておくことが重要です。 Id とテナントパラメーターにも同じことが当てはまります。 次のトピックでは、さまざまな Skype for Business の Web コマンドレットで Id、スコープ、テナントパラメーターを使用する方法について説明します。

  - [グローバルスコープのみを使用する Skype for Business Online のコマンドレット](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [グローバルスコープとタグスコープを使う Skype for Business Online のコマンドレット](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [ユーザー id を使用する Skype for Business Online のコマンドレット](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [ユーザー id とタグのスコープを使う Skype for Business Online のコマンドレット](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [テナントパラメーターを使う Skype for Business Online のコマンドレット](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [会議プロバイダー id を使用する Skype for Business Online のコマンドレット](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [スコープまたは id を使用しない Skype for Business Online のコマンドレット](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

