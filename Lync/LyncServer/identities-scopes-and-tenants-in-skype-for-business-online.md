---
title: Skype for Business Online の id、スコープ、およびテナント
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 598f1cb760a6b4ca969c1e8df25f9735fd0df7c1
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>Skype for Business Online の id、スコープ、およびテナント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-03-09_

Skype for Business Online を管理するために使用されている Windows PowerShell コマンドレットの多くは、管理しようとしているアイテムについて明確にする必要があります。 たとえば、 [Csuser acp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)コマンドレットを実行するときは、管理するユーザーを指定する必要があります。 これは、理にかなっています。 コマンドレットに管理するユーザーアカウントを特に指定しない限り、ユーザーの電話会議情報をどのユーザーに対して変更する必要があるか**は、このコマンドレットに**はわかりません。 このため、 **Set-CsUserAcp**コマンドレットを実行するたびに、identity パラメーターを含める必要があります。その後に、変更するユーザーアカウントの id を指定する必要があります。

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

用語*id*が常にユーザーアカウントの id を参照している場合、混乱が生じることはほとんどありません。 ユーザー (ユーザー、連絡先など) を扱う場合、Id は個別のユーザーを参照します。 ただし、ユーザーアカウント以外のアイテムにも Id があります。 Skype for Business Online サービスのコンポーネント (ポリシー、構成設定など) を処理している場合は、用語 Id は、多少異なるものになります。 たとえば、次のコマンドを考えてみます。

    Get-CsMeetingConfiguration -Identity "global"

この例では、Id "global" は会議の構成設定の範囲を参照します。 *Scope*は、管理の球体を指定するために Skype For business Online (および Lync Server) で使用される用語です。 既定では、ポリシーと設定は常にグローバルスコープになります。 最初に Skype for Business Online アカウントをセットアップすると、グローバルなポリシーと設定のコレクション (グローバルな会議の構成設定、グローバル外部アクセスポリシー、グローバルなダイヤルプランなど) が既定で作成されます。

これらのグローバルポリシーと設定は、Microsoft Lync Server 2010 で導入されました。すべてのユーザーとすべてのコンポーネントを常に管理することができるようにします。 これは、Microsoft Office Communicator 2007 R2 では必ずしも当てはまりません。 システムにアクセスした方法によっては、ほぼ管理されていない状態になる可能性があります (多くの場合、グループポリシーをユーザーアカウントに適用できないため)。 一方、Lync Server と Skype for Business Online では、管理されていないものはありません。 これは、他のすべての代わりに、グローバルポリシーと設定が常に適用されるためです。

「Else」とは何を意味していますか? Skype for Business Online の場合、*タグのスコープ*または管理の球体でポリシーを作成することができます。 タグスコープ (*ユーザーごとのスコープ*とも呼ばれる) で作成されたポリシーは、グローバルスコープで作成されたポリシーより優先されます。 言い換えると、ユーザーごとのポリシーは常にグローバルポリシーよりも優先されます。 たとえば、2つの外部ユーザーアクセスポリシーがあるとします。 グローバルポリシーにより、ユーザーは、パブリックインスタントメッセージング (IM) プロバイダー (Windows Live など) のアカウントを持つユーザーと通信することができなくなります。 ユーザーごとのポリシーである AllowPublicIMCommunication は、パブリック IM プロバイダーとの通信を可能にします。

また、Ken Myer と Pilar Ackerman という2人のユーザーがいる場合もあります。 Ken Myer には、ユーザーごとのポリシーが割り当てられています。 Pilar Ackerman にはユーザーごとのポリシーが割り当てられていません。つまり、彼女はグローバル外部アクセスポリシーによって管理されます。 次の表は、パブリック IM プロバイダーと通信できるユーザー (ある場合) を示しています。


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
<td><p>ユーザーがパブリック IM プロバイダーと通信できる</p></td>
<td><p>はい</p></td>
<td><p>いいえ</p></td>
</tr>
</tbody>
</table>


ご覧のとおり、Ken Myer はパブリック IM プロバイダーと通信することができます。 これは、ユーザーごとに割り当てられたポリシーの設定がグローバルポリシーの設定より優先されるためです。 Pilar Ackerman はパブリック IM プロバイダーと通信できません。 これは、グローバルポリシーによって管理されているため、グローバルポリシーによってそのような通信が禁止されるためです。

Microsoft サポートによって、ユーザーごとのポリシーを作成する必要があります。 ポリシーが作成されたら、適切な**付与**されたコマンドレット (たとえば、 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)) を使用して、ポリシーをユーザーに割り当てることができます。 ポリシーの Id は常にタグ**プレフィックス**で始まるため、ユーザーごとのポリシーは簡単に識別できます。 例:

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> タグ<STRONG>プレフィックス</STRONG>の日付は、Lync Server 2010 の早期の開発日に戻されます。 このような場合、ユーザーごとのポリシーは<EM>タグポリシー</EM>と呼ばれ、タグの<STRONG>プレフィックス</STRONG>によって識別されていました。 これらのポリシーは、<EM>ユーザーごとのポリシー</EM>としてより正確に参照されるようになり、タグの範囲は<EM>ユーザー単位のスコープ</EM>としてより正確に参照されます。 ただし、技術的な理由から、タグの<STRONG>プレフィックス</STRONG>は変更されていません。



</div>

Skype for Business Online および Windows PowerShell の使用時に使用されるもう1つの重要な用語は*テナント*です。 Skype for Business Online アカウントをセットアップすると、新しい展開には、次のようなグローバル一意識別子 (GUID) を持つテナント ID 番号が割り当てられます。

    bf19b7db-6960-41e5-a139-2aa373474354

いくつかの Skype for Business Online コマンドレットでは、コマンドレットを実行するたびに、テナント ID を入力する必要があります。 テナント ID は、1つのテナントにログオンしている場合でも、1つのテナントに対してのみ入力する必要があります。 さいわい、テナント ID を記憶する必要はありません。 テナント ID は、次の Windows PowerShell コマンドを実行することによって、いつでも取得できます。

    Get-CsTenant | Select-Object TenantId

当然ですが、グローバルスコープとユーザーごとのスコープ (またはタグのスコープ) の違いについては、半分の戦いに過ぎません。 また、どのような場合でも、これらの範囲を使用できるかどうかを知ることが重要です。 Identity と tenant パラメーターにも同じことが当てはまります。 次のトピックでは、さまざまな Skype for Business Online コマンドレットが Id、範囲、およびテナントパラメーターを使用する方法について説明します。

  - [グローバルスコープのみを使用する Skype for Business Online のコマンドレット](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [グローバルスコープとタグスコープを使用する Skype for Business Online のコマンドレット](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [ユーザー id を使用する Skype for Business Online のコマンドレット](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [ユーザー id とタグスコープを使用する Skype for Business Online のコマンドレット](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [テナントパラメーターを使用する Skype for Business Online のコマンドレット](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [電話会議プロバイダーの id を使用する Skype for Business Online のコマンドレット](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [スコープまたは id を使用しない Skype for Business Online のコマンドレット](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

