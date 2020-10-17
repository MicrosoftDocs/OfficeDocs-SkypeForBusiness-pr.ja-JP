---
title: ダイヤルイン会議の暗証番号 (PIN) ルールを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b446d38b3a2a2c054619373a605192ca05886174
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537204"
---
# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a>Lync Server 2013 でダイヤルイン会議の暗証番号 (PIN) ルールを構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-19_

Lync Server 2013 組織内の Active Directory ドメインサービス (AD DS) の資格情報を持つユーザーは、個人識別番号 (PIN) を使用して、認証されたユーザーとしてダイヤルイン会議に参加できます。 PIN ポリシーは、ダイヤルイン会議の Pin の動作規則を定義します。

特定のポリシーをサイトまたは特定のユーザーグループに適用する場合は、新しい PIN ポリシーを作成できます。 組織全体で同じ PIN ポリシーを使用する場合は、グローバル PIN ポリシーを使用して、必要に応じて変更することができます。 PIN ポリシーは、最も狭いスコープから最も広いスコープへのユーザーに適用されます。 ユーザーレベルの PIN ポリシーをユーザーに割り当てると、それらの設定が優先されます。 ユーザーポリシーを割り当てない場合は、サイトレベルの PIN ポリシーが適用されます (存在する場合)。 ユーザーポリシーまたはサイトポリシーが適用されていない場合は、グローバル PIN ポリシーが既定の設定を提供します。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での既定のダイヤルイン会議の PIN 設定の変更](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [サイトまたはユーザーのグループに対して Lync Server 2013 でダイヤルイン会議の PIN 設定を作成または変更する](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [Lync Server 2013 で、サイトまたはユーザーのグループのダイヤルイン会議の PIN 設定を削除する](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

