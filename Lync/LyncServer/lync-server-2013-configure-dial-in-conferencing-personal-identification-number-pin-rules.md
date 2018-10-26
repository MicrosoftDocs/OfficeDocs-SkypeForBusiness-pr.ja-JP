---
title: ダイヤルイン会議の暗証番号 (PIN) ルールの構成
TOCTitle: ダイヤルイン会議の暗証番号 (PIN) ルールの構成
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48271609
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ダイヤルイン会議の暗証番号 (PIN) ルールの構成

 

_**トピックの最終更新日:** 2012-06-19_

組織の Active Directory ドメイン サービス (AD DS) の資格情報を持つ Lync Server 2013 ユーザーは、暗証番号 (PIN) を使用することで、認証済みユーザーとしてダイヤルイン会議に参加できます。PIN ポリシーは、ダイヤルイン会議 PIN がどのように機能するかについてのルールを定義します。

特定のポリシーをサイトまたは特定のユーザー グループに適用する場合は、新しい PIN ポリシーを作成できます。 組織全体で同じ PIN ポリシーを使用する場合は、グローバル PIN ポリシーを使用でき、必要に応じて変更することもできます。 PIN ポリシーは、最も狭いスコープから最も広いスコープまでのどのスコープでも、ユーザーに適用されます。 ユーザーレベルの PIN ポリシーをユーザーに割り当てると、それらの設定は優先権を持ちます。 ユーザー ポリシーを割り当てない場合は、サイトレベルの PIN ポリシーがあれば、そのポリシーが適用されます。 ユーザー ポリシーもサイト ポリシーも適用されていない場合は、グローバル PIN ポリシーが既定の設定を提供します。

## このセクション中

  - [Lync Server 2013 での既定のダイヤルイン会議の PIN 設定の変更](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [サイトまたはユーザーのグループ向けに Lync Server 2013 でダイヤルイン会議の PIN 設定を作成または変更する](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [サイトまたはユーザーのグループのダイヤルイン会議の PIN 設定を削除する](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

