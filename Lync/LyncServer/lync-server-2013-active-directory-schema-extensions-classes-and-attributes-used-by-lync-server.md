---
title: 'Lync Server 2013: Lync Server が使用する Active Directory のスキーマ拡張、クラス、属性'
TOCTitle: Lync Server 2013 が使用する Active Directory のスキーマ拡張、クラス、属性
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48272143
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 が使用する Active Directory のスキーマ拡張、クラス、属性

 

_**トピックの最終更新日:** 2012-06-19_

このリファレンス セクションの内容は、次のとおりです。

  - Lync Server 2013 の新しいあるいは変更された Active Directory スキーマ拡張
    
    Active Directory スキーマには、Active Directory フォレスト内に作成できるすべてのオブジェクト クラスの正式な定義と、Active Directory オブジェクトで使用できるすべての属性の正式な定義が含まれています。Active Directory グローバル カタログには、フォレストのすべてのオブジェクトのレプリカと、各オブジェクトの属性のサブセットが含まれています。 ここでは、Lync Server 2013 の新しいあるいは変更されたクラスおよび属性について説明します。

  - Lync Server が使用するすべてのクラス (それぞれの説明付き)

  - Lync Server が使用するすべての属性 (それぞれの説明付き)

  - Lync Server が使用するクラスの一覧 (含まれる場合はそれぞれの属性付き)

  - グローバル設定とオブジェクト、およびフォレストの準備中に作成されたユニバーサル サービス グループとユニバーサル管理グループ

  - ドメインの準備中にドメイン ルートおよび組み込みコンテナーに作成されたアクセス制御エントリ (ACE)

  - Grant\_CsSetupPermission コマンドレットによって Active Directory の組織単位 (OU) に対して行われる変更

  - Grant\_CsOUPermission コマンドレットによって Active Directory の OU に対して行われる変更

## このセクション中

  - [Lync Server 2013 のスキーマの変更](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [Lync Server 2013 でのスキーマのクラスと説明](lync-server-2013-schema-classes-and-descriptions.md)

  - [Lync Server 2013 でのスキーマの属性と説明](lync-server-2013-schema-attributes-and-descriptions.md)

  - [Lync Server 2013 でのクラスごとのスキーマの属性](lync-server-2013-schema-attributes-by-class.md)

  - [Lync Server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)

  - [Lync Server 2013 でのドメインの準備によって加えられる変更](lync-server-2013-changes-made-by-domain-preparation.md)

  - [Lync Server 2013 での Grant-CsSetupPermission によって行われる変更](lync-server-2013-changes-made-by-https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission)

  - [Lync Server 2013 での Grant-CsOUPermission によって行われる変更](lync-server-2013-changes-made-by-https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission)

