---
title: 'Lync Server 2013: フォレストの準備'
TOCTitle: フォレストの準備
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48271838
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのフォレストの準備

 

_**トピックの最終更新日:** 2013-02-21_

フォレストの準備では、Lync Server 2013 で使用するための Active Directory のグローバル設定およびオブジェクトと、Active Directory ユニバーサル グループが作成され、Active Directory オブジェクトに適切なアクセス許可が与えられます。フォレストの準備で作成される、ユニバーサル グループ、およびグローバル設定とオブジェクトの詳細については、「[Lync Server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)」を参照してください。

フォレストの準備では、Lync Server 2013 で使用されるプロパティ セットと表示指定子が格納されるオブジェクトも作成し、これを構成コンテナーに保存します。


> [!IMPORTANT]
> フォレストの準備の手順を実行する前に、スキーマ準備の変更がすべてのドメイン コントローラーにレプリケートされていることを確認します。 レプリケーションが完了していない場合は、エラーが発生します。



新しい Lync Server の展開を実行している場合は、構成コンテナーにグローバル設定を格納する必要があります。以前のバージョンからアップグレードしており、引き続きシステム コンテナーにグローバル設定を格納する場合は、システム コンテナーを使用し続けることができます。

この手順を実行するには、フォレストのルート ドメインの Enterprise Admins グループまたは Domain Admins グループのメンバーである必要があります。

## このセクション中

  - [Lync Server 2013 でのフォレストの準備の実行](lync-server-2013-running-forest-preparation.md)

  - [コマンドレットの使用による Lync Server 2013 のフォレストの準備のリバース](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

