# Appwebconfig
## Crear esquema en mysqlworkbench
##### Este debe tener el nombre de la database
## No olvidar configurar la contra y todo en el appsetting.json
##### Ejemplo referencial: "DefaultConnection": "server=localhost; port= 3306; user=root; password=mysql1234; database=pecuario_pro"
## Copiar esto en el solution / launchsettings.json
{
  "$schema": "http://json.schemastore.org/launchsettings.json",
  "iisSettings": {
    "windowsAuthentication": false,
    "anonymousAuthentication": true,
    "iisExpress": {
      "applicationUrl": "http://localhost:1469",
      "sslPort": 44322
    }
  },
  "profiles": {
    "http": {
      "commandName": "Project",
      "dotnetRunMessages": true,
      "launchBrowser": true,
      "launchUrl": "swagger",
      "applicationUrl": "http://localhost:5147",
      "environmentVariables": {
        "ASPNETCORE_ENVIRONMENT": "Development"
      }
    },
    "https": {
      "commandName": "Project",
      "dotnetRunMessages": true,
      "launchBrowser": true,
      "launchUrl": "swagger",
      "applicationUrl": "https://localhost:7299;http://localhost:5147",
      "environmentVariables": {
        "ASPNETCORE_ENVIRONMENT": "Development"
      }
    },
    "IIS Express": {
      "commandName": "IISExpress",
      "launchBrowser": true,
      "launchUrl": "swagger",
      "environmentVariables": {
        "ASPNETCORE_ENVIRONMENT": "Development"
      }
    }
  }
}



{
        /// <summary>
        /// Obtiene o establece el identificador de la orden de compra.
        /// </summary>
        [Key]
        [DatabaseGenerated(DatabaseGeneratedOption.Identity)]
        public int Id { get; private set; }

        /// <summary>
        /// Obtiene o establece el cliente asociado a la orden de compra.
        /// </summary>
        [Required]
        public string Customer { get; private set; }

        /// <summary>
        /// Obtiene o establece el identificador del tejido.
        /// </summary>
        [Required]
        public int FabricId { get; private set; }

        /// <summary>
        /// Obtiene o establece la ciudad asociada a la orden de compra.
        /// </summary>
        [Required]
        public string City { get; private set; }

        /// <summary>
        /// Obtiene o establece la URL del resumen asociado a la orden de compra.
        /// </summary>
        [Required]
        public string ResumeUrl { get; private set; }

        /// <summary>
        /// Obtiene o establece la cantidad de la orden de compra.
        /// </summary>
        [Required]
        public int Quantity { get; private set; }

        /// <summary>
        /// Inicializa una nueva instancia de la clase <see cref="PurchaseOrder"/>.
        /// </summary>
        /// <param name="customer">El cliente asociado a la orden de compra.</param>
        /// <param name="fabricId">El identificador del tejido.</param>
        /// <param name="city">La ciudad asociada a la orden de compra.</param>
        /// <param name="resumeUrl">La URL del resumen asociado a la orden de compra.</param>
        /// <param name="quantity">La cantidad de la orden de compra.</param>
        public PurchaseOrder(string customer, int fabricId, string city, string resumeUrl, int quantity)
        {
            Customer = customer;
            FabricId = fabricId;
            City = city;
            ResumeUrl = resumeUrl;
            Quantity = quantity;
        }
    }