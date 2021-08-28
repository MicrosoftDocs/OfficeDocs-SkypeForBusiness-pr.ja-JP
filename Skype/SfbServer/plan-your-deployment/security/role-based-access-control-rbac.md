---
title: ユーザーの役割ベースのアクセス制御 (RBAC) Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype for Business ServerにはRole-Basedアクセス制御 (RBAC) グループが含まれています。 これらのグループはフォレストの準備の際に作成されます。 フォレストの準備の詳細については、「Active Directory Domain Services for Skype for Business Server。 フォレストの準備によって作成された特定のグループの詳細については、「展開」のドキュメントの「Skype for Business Serverフォレストの準備によって行われた変更」を参照してください。
ms.openlocfilehash: 1768c61f902dddb456f6a80bccf3b72bd9757f77
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627939"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>ユーザーの役割ベースのアクセス制御 (RBAC) Skype for Business Server
 
Skype for Business ServerにはRole-Basedアクセス制御 (RBAC) グループが含まれています。 これらのグループはフォレストの準備の際に作成されます。 フォレストの準備の詳細については[、「Active Directory Domain Services for Skype for Business Server」 を参照してください](active-directory-domain-services.md)。 フォレストの準備によって作成された特定のグループの詳細については、「展開」のドキュメントの「Skype for Business Serverフォレストの準備[によって行われた](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)変更」を参照してください。
  
RBAC を使用すると、多くの一般的な管理タスクをカバーする 11 の定義済みの役割を含む、定義済みの管理役割にユーザーを割り当てると、管理特権が付与されます。 各役割は、その役割のユーザーがSkype for Business Server許可されている管理シェル コマンドレットの特定の一覧に関連付けられる。 RBAC を使用すると、ジョブに必要な管理能力のみをユーザーに与える "最小特権" の原則に従います。 
  
RBAC の役割の詳細については、「役割ベースのアクセス制御の計画 [」を参照してください](/lyncserver/lync-server-2013-planning-for-role-based-access-control)。