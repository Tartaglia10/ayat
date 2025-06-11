# ayat
lo07

#outil>soutenancz_2025_create.sql
#verifier que ca fonctionne

CREATE TABLE personne ( #incomplet
  id INTEGER UNSIGNED NOT NULL,
  nom VARCHAR(45) NOT NULL,
  prenom VARCHAR(45) NOT NULL,
  role_responsable BOOLEAN,
  role_examinateur BOOLEAN,
  role_etudiant BOOLEAN,
  login_prsn VARCHAR(45) NOT NULL,
  password_prsn VARCHAR(45) NOT NULL,
  PRIMARY KEY(id)
)  ENGINE=InnoDB DEFAULT CHARACTER SET=utf8;

CREATE TABLE projet (
  id INTEGER UNSIGNED NOT NULL,
  label VARCHAR(45) NOT NULL,
  responsable VARCHAR(45) NOT NULL,
  groupe INTEGER UNSIGNED NOT NULL,
  PRIMARY KEY(id)
) ENGINE=InnoDB DEFAULT CHARACTER SET=utf8;

CREATE TABLE creneau (
  creneau_id INTEGER UNSIGNED NOT NULL,
  FOREIGN KEY(projet_id) REFERENCES projet(id),
  FOREIGN KEY(examinateur_id) REFERENCES personne(id),
  creaneau
) ENGINE=InnoDB DEFAULT CHARACTER SET=utf8;

CREATE TABLE rdv (
  rdv_id INTEGER UNSIGNED NOT NULL,
  FOREIGN KEY(creneau_id) REFERENCES creneau(id),
  FOREIGN KEY(etudiant_id) REFERENCES personne(id)
) ENGINE=InnoDB DEFAULT CHARACTER SET=utf8;



