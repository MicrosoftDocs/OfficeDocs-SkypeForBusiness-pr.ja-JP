---
title: Skype for Business Server 2015 の役割ベースのアクセス制御 (RBAC)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: ビジネス サーバー 2015 の Skype には、高水準のセキュリティを維持しながら管理タスクを委任できるようにするための役割に基づくアクセス制御 (RBAC) グループが含まれています。 これらのグループはフォレストの準備の際に作成されます。 フォレストの準備に関する詳細については、ビジネス サーバー 2015 の Skype 用の Active Directory ドメイン サービスを参照してください。 フォレストの準備によって作成された特定のグループに関する詳細については、フォレストの準備で Skype ビジネス サーバーの展開に関するドキュメントでの変更を参照してください。
ms.openlocfilehash: f637ef752bb122cb73220d66fd8aa19c16fb358e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 の役割ベースのアクセス制御 (RBAC)
 
ビジネス サーバー 2015 の Skype には、高水準のセキュリティを維持しながら管理タスクを委任できるようにするための役割に基づくアクセス制御 (RBAC) グループが含まれています。 これらのグループはフォレストの準備の際に作成されます。 フォレストの準備に関する詳細については、[ビジネス サーバー 2015 の Skype 用の Active Directory ドメイン サービス](active-directory-domain-services.md)を参照してください。 フォレストの準備によって作成された特定のグループに関する詳細情報は、展開に関するドキュメントで[ビジネス サーバーの Skype でのフォレストの準備によって変更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)を参照してください。
  
Rbac では、管理者特権が付与された定義済みの管理者ロールにユーザーを割り当てることによりなど多くの一般的な管理タスクをカバーする 11 の定義済みのロールです。 各役割は、Lync Server 管理シェル コマンドレットを実行するのにはそのロール内のユーザーが許可されているは特定のリストに関連付けられます。 「最低限の特権」の原則に従う RBAC を使用するにはで、ユーザーの業務で必要とされる管理権限のみが与えられます。 
  

