# comptages-decadaires
Sous-module Monitoring pour le Comptage décadaire d'oiseaux


memo

value : "({value, meta}) => {return value.observers = meta.id_role}"


    "const observers = (meta.id_role);",
      "if (objForm.controls.observers.pristine) {",
          "objForm.patchValue({observers})",
      "}",

    "const observers = (meta.id_role);",
    "(objForm.value.observers == (null || undefined)  ? objForm.patchValue({observers}) : '');",