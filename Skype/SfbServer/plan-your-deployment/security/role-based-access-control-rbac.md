---
title: Skype ビジネス サーバーの役割に基づくアクセス制御 (RBAC)
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype ビジネス サーバー用には、高水準のセキュリティを維持しながら管理タスクを委任できるようにするための役割に基づくアクセス制御 (RBAC) グループが含まれています。 これらのグループはフォレストの準備の際に作成されます。 フォレストの準備に関する詳細については、ビジネスのサーバーの Skype 用の Active Directory ドメイン サービスを参照してください。 フォレストの準備によって作成された特定のグループに関する詳細については、フォレストの準備で Skype ビジネス サーバーの展開に関するドキュメントでの変更を参照してください。
ms.openlocfilehash: b0029ec683bec29da187ecd23dd0c3230fc603a5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967692"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Skype ビジネス サーバーの役割に基づくアクセス制御 (RBAC)
 
Skype ビジネス サーバー用には、高水準のセキュリティを維持しながら管理タスクを委任できるようにするための役割に基づくアクセス制御 (RBAC) グループが含まれています。 これらのグループはフォレストの準備の際に作成されます。 フォレストの準備に関する詳細については、 [Skype のビジネス サーバーの Active Directory ドメイン サービス](active-directory-domain-services.md)を参照してください。 フォレストの準備によって作成された特定のグループに関する詳細情報は、展開に関するドキュメントで[ビジネス サーバーの Skype でのフォレストの準備によって変更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)を参照してください。
  
Rbac では、管理者特権が付与された定義済みの管理者ロールにユーザーを割り当てることによりなど多くの一般的な管理タスクをカバーする 11 の定義済みのロールです。 各役割は、Lync Server 管理シェル コマンドレットを実行するのにはそのロール内のユーザーが許可されているは特定のリストに関連付けられます。 「最低限の特権」の原則に従う RBAC を使用するにはで、ユーザーの業務で必要とされる管理権限のみが与えられます。 
  
RBAC の役割の詳細についてはにあります。https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx
