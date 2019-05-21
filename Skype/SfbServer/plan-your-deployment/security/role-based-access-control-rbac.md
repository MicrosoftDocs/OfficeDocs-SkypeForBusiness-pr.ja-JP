---
title: Skype for Business Server の役割ベースのアクセス制御 (RBAC)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype for Business Server には役割ベースのアクセス制御 (RBAC) グループが含まれているので、セキュリティの高い標準を維持しながら、管理タスクを委任できます。 これらのグループはフォレストの準備の際に作成されます。 フォレストの準備の詳細については、「Skype for Business Server の Active Directory ドメインサービス」を参照してください。 フォレストの準備によって作成される特定のグループの詳細については、展開ドキュメントの「Skype for Business Server でのフォレストの準備による変更」を参照してください。
ms.openlocfilehash: 493af102ae42658d51cfcb5d65fde6c26596d82d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296841"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Skype for Business Server の役割ベースのアクセス制御 (RBAC)
 
Skype for Business Server には役割ベースのアクセス制御 (RBAC) グループが含まれているので、セキュリティの高い標準を維持しながら、管理タスクを委任できます。 これらのグループはフォレストの準備の際に作成されます。 フォレストの準備の詳細については、「 [Skype For Business Server の Active Directory ドメインサービス](active-directory-domain-services.md)」を参照してください。 フォレストの準備によって作成される特定のグループの詳細については、展開ドキュメントの「 [Skype For Business Server でのフォレストの準備による変更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)」を参照してください。
  
RBAC では、管理者特権が与えられているのは、事前に定義された管理者ロールにユーザーを割り当てることによって、多くの一般的な管理タスクに適用される11定義済みのロールを含むことです 各役割は、その役割のユーザーが実行できる Lync Server 管理シェルコマンドレットの特定のリストに関連付けられています。 RBAC を使うと、ユーザーに対して、自分のジョブで必要な管理機能のみが与えられる、"最低限の権限" の原則に従うことができます。 
  
RBAC の役割の詳細については、次のページを参照してください。https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx
