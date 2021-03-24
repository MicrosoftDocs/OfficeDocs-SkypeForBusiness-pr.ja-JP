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
description: Skype for Business Server には、Role-Basedアクセス制御 (RBAC) グループが含まれています。 これらのグループはフォレストの準備の際に作成されます。 フォレストの準備の詳細については、「Active Directory Domain Services for Skype for Business Server」を参照してください。 フォレストの準備によって作成された特定のグループの詳細については、「展開」のドキュメントの「Skype for Business Server のフォレスト準備によって行われた変更」を参照してください。
ms.openlocfilehash: e02123721433e2af0ca3576ac71dd5a49a0ad9a1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104213"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Skype for Business Server の役割ベースのアクセス制御 (RBAC)
 
Skype for Business Server には、Role-Basedアクセス制御 (RBAC) グループが含まれています。 これらのグループはフォレストの準備の際に作成されます。 フォレストの準備の詳細については [、「Active Directory Domain Services for Skype for Business Server」を参照してください](active-directory-domain-services.md)。 フォレストの準備によって作成された特定のグループの詳細については、「展開」のドキュメントの [「Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) のフォレスト準備によって行われた変更」を参照してください。
  
RBAC を使用すると、多くの一般的な管理タスクをカバーする 11 の定義済みの役割を含む、定義済みの管理役割にユーザーを割り当てると、管理特権が付与されます。 各役割は、その役割のユーザーが実行を許可する Skype for Business Server 管理シェル コマンドレットの特定のリストに関連付けられる。 RBAC を使用すると、ジョブに必要な管理能力のみをユーザーに与える "最小特権" の原則に従います。 
  
RBAC の役割の詳細については、「役割ベースのアクセス制御の計画 [」を参照してください](/lyncserver/lync-server-2013-planning-for-role-based-access-control)。