---
title: Skype for Business Server の役割ベースのアクセス制御 (RBAC)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype for Business Server には、Role-Basedアクセス制御 (RBAC) グループが含まれています。このグループを使用すると、高いセキュリティ基準を維持しながら管理タスクを委任できます。 これらのグループはフォレストの準備の際に作成されます。 フォレストの準備の詳細については、「Active Directory Domain Services for Skype for Business Server」を参照してください。 フォレストの準備によって作成される特定のグループの詳細については、「展開」のドキュメントの「Skype for Business Server でのフォレストの準備によって行われた変更」を参照してください。
ms.openlocfilehash: 9d3c453d4e7c3057c03f99cf2ff31b5fe17ae0bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832107"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Skype for Business Server の役割ベースのアクセス制御 (RBAC)
 
Skype for Business Server には、Role-Basedアクセス制御 (RBAC) グループが含まれています。このグループを使用すると、高いセキュリティ基準を維持しながら管理タスクを委任できます。 これらのグループはフォレストの準備の際に作成されます。 フォレストの準備の詳細については [、「Skype for Business Server の Active Directory ドメイン サービス」を参照してください](active-directory-domain-services.md)。 フォレストの準備によって作成される特定のグループの詳細については、「展開」のドキュメントの [「Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) でのフォレストの準備によって行われた変更」を参照してください。
  
RBAC を使用すると、多くの一般的な管理タスクを対象にした 11 の定義済みの役割を含む、定義済みの管理役割にユーザーを割り当てると、管理特権が付与されます。 各役割は、その役割のユーザーが実行を許可されている特定の Skype for Business Server 管理シェル コマンドレットの一覧に関連付けられている。 RBAC を使用すると、"最小特権" という原則に従って、ユーザーにはジョブに必要な管理機能だけが与えられます。 
  
RBAC の役割の詳細については、「役割ベースのアクセス制御の計画」 [を参照してください](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)。
