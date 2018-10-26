---
title: Lync Server 2013 の役割ベースのアクセス制御 (RBAC)
TOCTitle: Lync Server 2013 の役割ベースのアクセス制御 (RBAC)
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59679289
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の役割ベースのアクセス制御 (RBAC)

 

_**トピックの最終更新日:** 2013-11-07_

Microsoft Lync Server 2013 には役割ベースのアクセス制御 (RBAC) グループが含まれており、高いレベルのセキュリティを維持しながら管理タスクを委任できます。これらのグループはフォレストの準備の際に作成されます。フォレストの準備について詳しくは、「[Lync Server 2013 用の Active Directory ドメイン サービス](lync-server-2013-active-directory-domain-services-for-lync-server.md)」をご覧ください。フォレストの準備によって作成される特定のグループについて詳しくは、展開のドキュメントの「[Lync Server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)」をご覧ください。

RBAC では、定義済みの管理者の役割にユーザーを割り当てることにより、管理者特権が付与されます。これには、多くの一般的な管理タスクに対応する 11 個の定義済みの役割が含まれています。各役割には、その役割のユーザーが実行できる Lync Server 管理シェル コマンドレットの具体的な一覧が関連付けられています。RBAC を使用すると、業務上必要な管理能力のみをユーザーに与える "最小限の特権" の原則に従うことができます。詳しくは、計画のドキュメントの「[Lync Server 2013 での役割ベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」をご覧ください。

